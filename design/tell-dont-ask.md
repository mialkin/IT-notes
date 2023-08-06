# Tell Don't Ask

**Tell, Don't Ask** or **TDA** is a principle that suggests that it is better to issue an object a command do perform some operation or logic, rather than to query its state and then take some action as a result.

It is related to the [↑ Flags Over Objects](https://deviq.com/antipatterns/flags-over-objects) anti-pattern as well as the [Anemic Domain Model](ddd.md#anemic-domain-model) anti-pattern. You can easily spot violations of TDA in code that queries or uses several properties of an object in order to perform some calculation. This is especially problematic when the same kind of calculation is done in many places, violating the Don't Repeat Yourself principle, but can represent a design deficiency even if it only occurs in one location in the current codebase.

## Example

Code, that violates TDA principle:

```csharp
public record CpuMonitor(int Value);

public class Client
{
    public static void AlertService(IEnumerable<CpuMonitor> cpuMonitors)
    {
        foreach (var cpuMonitor in cpuMonitors)
        {
            if (cpuMonitor.Value > 90)
            {
                // Alert
            }
        }
    }
}
```

Refactored version of the code above:

```csharp
public class CpuMonitor
{
    private readonly int _alertThreshold;
    public CpuMonitor(int alertThreshold) => _alertThreshold = alertThreshold;
    public int Value { get; set; }
    public bool ExceedsThreshold => Value >= _alertThreshold;
}

public class Client
{
    public static void AlertService(IEnumerable<CpuMonitor> cpuMonitors)
    {
        foreach (var cpuMonitor in cpuMonitors)
        {
            if (cpuMonitor.ExceedsThreshold)
            {
                // Alert
            }
        }
    }
}
```

Refactored further:

```csharp
public class CpuMonitor
{
    private readonly int _alertThreshold;
    private readonly Action<CpuMonitor> _alertAction;

    public CpuMonitor(int alertThreshold, Action<CpuMonitor> alertAction)
    {
        _alertThreshold = alertThreshold;
        _alertAction = alertAction;
    }

    public int Value { get; set; }
    private bool ExceedsThreshold => Value >= _alertThreshold;

    public void Sample()
    {
        if (ExceedsThreshold) 
            _alertAction(this);
    }
}

public class Client
{
    public static void AlertService(IEnumerable<CpuMonitor> cpuMonitors)
    {
        foreach (var cpuMonitor in cpuMonitors)
            cpuMonitor.Sample();
    }
}
```

In the example above, the first refactoring looks at the magic number representing the alert threshold, and moves this concept into the monitor itself. This might not be worth correcting if this client code were the only instance of this behavior, but if you find repetition in this kind of code, follow the Don't Repeat Yourself principle and consolidate it into a class, in this case, `CpuMonitor`. The initial refactoring is still querying each monitor and then performing some action based on that query, and so is still asking, not telling. The final refactoring moves the responsibility for sending alerts into the monitor itself, while still avoiding tightly coupling it to any particular alert implementation. In this way, monitor remains loosely coupled from whatever alert implementation the system might have in place.

It's not necessary to follow the "don't ask" part of this principle to the extreme of eliminating all access to objects' state. In general, it's ok to query an object for its state, provided the information isn't being used to make a decision related to the object. If it is, then that decision and any corresponding behavior should most likely be moved within the object itself. Another consequence of violating TDA is that often magic numbers or business rules end up sprinkled throughout code that references object state, rather than embedded within the object itself or passed into the object as a defined and well-named construct, such as `CpuAlertThreshold` in the example above.

## Links

[↑ Tell, Don't Ask](https://deviq.com/principles/tell-dont-ask).

[↑ TellDontAsk](https://martinfowler.com/bliki/TellDontAsk.html).
