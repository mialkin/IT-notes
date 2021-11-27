# Documenting notes

## TOC

- [Documenting notes](#documenting-notes)
  - [TOC](#toc)
  - [Tools](#tools)
  - [Unix](#unix)
  - [Databases](#databases)
  - [Software architecture and design](#software-architecture-and-design)
  - [Programming](#programming)
  - [Web](#web)
  - [Networking](#networking)
  - [Security](#security)
  - [Python](#python)
  - [.NET](#net)
  - [C&#35;](#c)
  - [Computer science](#computer-science)
  - [Miscellaneous](#miscellaneous)

## Tools

- [Ansible](tools/ansible/ansible.md)
- [Docker](tools/docker/docker.md)
  - [Dockerfile](tools/docker/dockerfiles.md)
  - [Docker Compose](tools/docker/docker%20compose.md)
- [Git](tools/git/git.md)
- [Grafana](tools/grafana.md)
- [Jenkins](tools/jenkins.md)
- Kubernetes
  - [cert-manager](tools/kubernetes/cert-manager.md)
  - [Flux](tools/kubernetes/flux.md)
  - [Helm](tools/kubernetes/helm.md)
  - [Istio](tools/kubernetes/istio.md)
  - [k3s](tools/kubernetes/k3s/k3s.md)
  - [Kiali](tools/kubernetes/kiali.md)
  - [kubectl](tools/kubernetes/kubectl.md)
- [MC](tools/mc.md)
- [Prometheus](tools/prometheus.md)
- [RabbitMQ](tools/rabbitmq/rabbitmq.md)
- [Redis](tools/redis.md)
- [Regular expressions](tools/regular%20expressions/regular%20expressions.md)
- Testing
  - [k6](tools/testing/k6/k6.md)
  - [Unit testing best practices](tools/testing/unit%20testing%20best%20practices.md)
  - [xUnit](tools/testing/xunit.md)

## Unix

- [Environment variables](unix/environment%20variables.md)
- [macOS](unix/macos/macos.md)
- [Ubuntu](unix/ubuntu.md)
- [Nginx](unix/nginx.md)
- [Shell](unix/shell/shell.md)
  - [Shell scripting](unix/shell/shell%20scripting.md)
- [Tools](unix/tools.md)
  - [crontab](unix/crontab.md)
  - [gpg](unix/gpg.md)
  - [ssh](unix/ssh.md)
  - [tmux](unix/tmux.md)
  - [vim](unix/vim.md)
- [User management](unix/user%20managment.md)

## Databases

- [ACID](databases/acid.md)
- [Isolation levels and read phenomena](databases/isolation%20levels.md)
- [PL/SQL](databases/oracle/plsql.md)
- [PostgreSQL](databases/postgres/postgres.md)
- [SQL Server](databases/sqlserver/sqlserver.md)
  - [T-SQL](databases/sqlserver/tsql.md)
- [EF Core tools](databases/efcore/efcoretools.md)

## Software architecture and design

- Architectural patterns
  - CQRS
- [Design patterns](design/design%20patterns/design%20patterns.md)
  - Creational
    - [Abstract Factory](design/design%20patterns/abstract%20factory.md)
    - [Builder](design/design%20patterns/builder.md)
    - [Dependency injection](design/design%20patterns/dependency%20injection.md)
    - [Factory Method](design/design%20patterns/factory%20method.md)
    - [Prototype](design/design%20patterns/prototype.md)
    - [Singleton](design/design%20patterns/singleton.md)
  - Structural
    - [Adapter](design/design%20patterns/adapter.md)
    - [Bridge](design/design%20patterns/bridge.md)
    - [Composite](design/design%20patterns/composite.md)
    - [Decorator](design/design%20patterns/decorator.md)
    - [Facade](design/design%20patterns/facade.md)
    - [Flyweight](design/design%20patterns/flyweight.md)
    - [Proxy](design/design%20patterns/proxy.md)
  - Behavioral
    - [Chain of Responsibility](design/design%20patterns/chain%20of%20responsibility.md)
    - [Command](design/design%20patterns/command.md)
    - Interpreter
    - [Iterator](design/design%20patterns/iterator.md)
    - [Mediator](design/design%20patterns/mediator.md)
    - [Memento](design/design%20patterns/memento.md)
    - [Observer](design/design%20patterns/observer.md)
    - [State](design/design%20patterns/state.md)
    - [Strategy](design/design%20patterns/strategy.md)
    - [Template Method](design/design%20patterns/template%20method.md)
    - [Visitor](design/design%20patterns/visitor.md)
- Design principles
  - [Composition over inheritance](design/composition%20over%20inheritance.md)
  - [DRY, KISS, separation of concerns, YAGNI](design/main%20principles.md)
  - [Explicit Dependencies Principle](design/explicit%20dependencies%20principle.md)
  - [SOLID](design/solid/solid.md)
    - [Single Responsibility Principle](design/solid/srp.md)
    - [Open-Closed Principle](design/solid/ocp.md)
    - [Liskov Substitution Principle](design/solid/lsp.md)
    - [Interface Segregation Principle](design/solid/isp.md)
    - [Dependency Inversion Principle](design/solid/dip/dip.md)

## Programming

- [Aggregation and composition](programming/aggregation%20and%20composition/aggregation%20and%20composition.md)
- [Arguments vs parameters](programming/argument%20vs%20parameter.md)
- [Idempotence](programming/idempotence.md)
- [Inversion of control (IoC)](programming/ioc/inversion%20of%20control.md)
- [Programming case types](programming/cases.md)
- [Scrum](programming/scrum/scrum.md)
- [Serialization](programming/serialization.md)

## Web

- [GraphQL](web/graphql.md)
- [gRPC](web/grpc.md)
- [OAuth](web/oauth.md)
- [OpenAPI](web/openapi.md)
- [OpenID Connect](web/oidc.md)

## Networking

- [Ports](networking/ports.md)
- [Sockets](networking/sockets.md)
- [TCP](networking/tcp.md)
- [Wireshark](networking/wireshark/wireshark.md)

## Security

- [Asymmetric cryptography](security/asymmetric%20cryptography.md)
- [Advanced Encryption Standard (AES)](security/aes.md)
- [Generating self-signed certificate](security/generating%20certificate.md)
- [TLS handshake](security/tls%20handshake.md)
- Web
  - [↑ Cross-site request forgery (XSRF or CSRF)](https://docs.microsoft.com/en-us/aspnet/core/security/anti-request-forgery)
  - [↑ Cross-site scripting XSS](https://docs.microsoft.com/en-us/aspnet/core/security/cross-site-scripting)

## Python

- [Python](python/python.md)
  - [Syntax](python/syntax.md)

## .NET

- [.NET CLI](dotnet/cli.md)
- [Dependency injection in .NET](dotnet/dependency%20injection%20dotnet.md)
- [Secret Manager tool](dotnet/secret%20manager.md)
- [PowerShell](dotnet/powershell.md)
  - [PowerShell scripting](dotnet/powershell%20scripting.md)

## C&#35;

- [Attributes](csharp/attributes.md)
  - [Nullable static analysis attributes](csharp/nullable%20static%20analysis%20attributes.md)
- [Concurrency](csharp/concurrency/concurrency.md)
  - [Asynchronous programming](csharp/concurrency/asynchronous%20programming.md)
    - [Asynchronous patterns](csharp/concurrency/asynchronous/asynchronous%20patterns.md)
    - [`Async`/`await` best practices](csharp/concurrency/asynchronous/async%20await%20best%20practices.md)
    - [`Async` lambdas](csharp/concurrency/asynchronous/async%20lambdas.md)
    - [Awaiting multiple tasks](csharp/concurrency/asynchronous/awaiting%20multiple%20tasks.md)
    - [Exceptions handling with `async` and `await`](csharp/concurrency/asynchronous/exceptions.md)
    - [Execution context](csharp/concurrency/asynchronous/execution%20context.md)
    - [Reporting task's progress](csharp/concurrency/asynchronous/reporting%20progress.md)
    - [Returning variable of `Task` type](csharp/concurrency/asynchronous/returning%20task.md)
    - [`ValueTask<T>`](csharp/concurrency/asynchronous/valuetask.md)
  - Asynchronous streams
    - [`IAsyncEnumerable<T>` interface](csharp/concurrency/iasyncenumerable.md)
  - [Parallel programming](csharp/concurrency/parallel%20programming.md)
  - [Dataflow programming](csharp/concurrency/dataflow%20programming.md)
  - [Reactive programming](csharp/concurrency/reactive%20programming.md)
  - [Cancellation](csharp/concurrency/cancellation.md)
  - [Collections](csharp/concurrency/collections/collections.md)
    - Thread-safe collections
      - `BlockingCollection<T>`, `ConcurrentBag<T>`, `ConcurrentDictionary<TKey,TValue>`, `ConcurrentQueue<T>`, `ConcurrentStack<T>`
    - [When to use a thread-safe collection](csharp/concurrency/collections/when%20to%20use%20thread-safe.md)
  - [Synchronization](csharp/concurrency/synchronization.md)
  - Synchronization primitives
    - [`Interlocked`](csharp/concurrency/synchronization%20primitives/interlocked.md)
    - [`Monitor`](csharp/concurrency/synchronization%20primitives/monitor.md)
    - [`Mutex`](csharp/concurrency/synchronization%20primitives/mutex.md)
    - [`ReaderWriterLockSlim`](csharp/concurrency/synchronization%20primitives/readerwriterlockslim.md)
    - [`Semaphore` and `SemaphoreSlim`](csharp/concurrency/synchronization%20primitives/semaphore.md)
    - [`SpinLock` and `SpinWait`](csharp/concurrency/synchronization%20primitives/spinlock%20and%20spinwait.md)
    - Thread interaction or signaling
      - [`Barrier`](csharp/concurrency/synchronization%20primitives/barrier.md)
      - [`CountdownEvent`](csharp/concurrency/synchronization%20primitives/contdownevent.md)
      - [`EventWaitHandle`, `AutoResetEvent`, `ManualResetEvent`, `ManualResetEventSlim`](csharp/concurrency/synchronization%20primitives/eventwaithandle.md)
  - [Threads and threading](csharp/concurrency/threads%20and%20threading.md)
  - Exercises
    - [Downloading web pages](csharp/concurrency/exercises/downloading%20pages.md)
- [Covariance and contravariance](csharp/covariance%20and%20contravariance.md)
- [Extension methods](csharp/extension%20methods.md)
- [`IEnumerable<T>`](csharp/ienumerable.md)
- [Indexers](csharp/indexers.md)
- [Keywords](csharp/keywords/keywords.md)
  - Modifiers
    - [`event`](csharp/keywords/event.md)
  - Contextual keywords
    - [`yield`](csharp/keywords/yield.md)
  - [`ref`, `out`, `in` (parameter modifiers)](csharp/keywords/ref%20out%20in.md)
- Selected classes
  - [`HttpClient`](csharp/libraries/httpclient.md)
  - [`Stopwatch`](csharp/libraries/stopwatch.md)
- Memory
  - [Garbage collector](csharp/memory/garbage%20collector.md)
  - [`GC`](csharp/memory/gc.md)
- Operators and expressions
  - [Equality operator](csharp/operators/equality%20operator.md)
  - [Lambda expressions](csharp/operators/lambda%20expressions.md)
- Types
  - [Value types](csharp/types/value%20types.md)
    - [Boxing and unboxing](csharp/types/boxing%20and%20unboxing.md)
    - [Enumeration types](csharp/types/enum.md)
    - [Structure types](csharp/types/struct.md)
    - Tuple types
    - [`ValueType` class](csharp/types/value%20type%20class.md)
  - [Reference types](csharp/types/reference%20types.md)
    - Built-in reference types
      - [`delegate`](csharp/types/delegate.md)
      - [`object`](csharp/types/object.md)
        - [Constructors](csharp/types/constructors.md)
        - [Why override `GetHashCode` when `Equals` is overriden](csharp/types/override%20gethashcode.md)
      - [`record`](csharp/types/record.md)
      - [`string`](csharp/types/string.md)
    - [Nullable reference types](csharp/types/nullable%20reference%20types.md)

## Computer science

- [Sorting algorithms](computer%20science/sorting%20algorithms.md)

## Miscellaneous

- [Application shortcuts](shortcuts.md)
- [Translation of terminology into Russian](translations.md)
