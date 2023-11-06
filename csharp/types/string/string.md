# `string`

The `string` keyword is an alias for [↑ `String`](https://learn.microsoft.com/en-us/dotnet/api/system.string); therefore, `String` and `string` are equivalent.

It's recommended to use `string` alias as it works even without `using System;`.

## Table of contents

- [`string`](#string)
  - [Table of contents](#table-of-contents)
  - [String](#string-1)
  - [String as a collection of `char`s](#string-as-a-collection-of-chars)
  - [`StringInfo`](#stringinfo)
  - [Passing string to a method](#passing-string-to-a-method)
  - [String interpolation](#string-interpolation)

## String

A **string** is an object of type `String` whose value is text. Internally, the text is stored as a sequential read-only collection of [↑ `Char`](https://learn.microsoft.com/en-us/dotnet/api/system.char) objects.

There's no null-terminating character at the end of a C# string; therefore a C# string can contain any number of embedded null characters `\0`. The `Length` property of a string represents the number of `Char` objects it contains, not the number of Unicode characters. To access the individual Unicode code points in a string, use the `StringInfo` object.

[↑ Strings and string literals](https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/strings/).

## String as a collection of `char`s

.NET uses the `Char` structure to represent Unicode code points by using UTF-16 encoding. The value of a `Char` object is its 16-bit numeric (ordinal) value.

A `String` object is a sequential collection of `Char` structures that represents a string of text. Most Unicode characters can be represented by a single `Char` object, but a character that is encoded as a base character, surrogate pair, and/or combining character sequence is represented by multiple `Char` objects. For this reason, a `Char` structure in a `String` object is not necessarily equivalent to a single Unicode character.

Because a single character can be represented by multiple `Char` objects, it is not always meaningful to work with individual `Char` objects. For instance, the following example converts the Unicode code points that represent the [↑ Aegean numbers](https://en.wikipedia.org/wiki/Aegean_numerals) zero through 9 to UTF-16 encoded code units. Because it erroneously equates `Char` objects with characters, it inaccurately reports that the resulting string has 20 characters.

## `StringInfo`

You can use the `StringInfo` class to work with text elements instead of individual `Char` objects. The following example uses the `StringInfo` object to count the number of text elements in a string that consists of the Aegean numbers zero through nine. Because it considers a surrogate pair a single character, it correctly reports that the string contains ten characters.

```csharp
string result = String.Empty;
for (int ctr = 0x10107; ctr <= 0x10110; ctr++)  // Part of the range of Aegean numbers.
    result += Char.ConvertFromUtf32(ctr);

Console.WriteLine(result); // 𐄇𐄈𐄉𐄊𐄋𐄌𐄍𐄎𐄏𐄐
Console.WriteLine(result.Length); // 20

StringInfo si = new (result);
Console.WriteLine(si.LengthInTextElements); // 10 characters
```

[↑ Character encoding in .NET](https://docs.microsoft.com/en-us/dotnet/standard/base-types/character-encoding-introduction)

[↑ Char Struct](https://docs.microsoft.com/en-us/dotnet/api/system.char)

## Passing string to a method

```csharp
string hello = "hello";
string world = "world";

Act(hello, ref world);

// The reference to the string "hello" is passed by value.
// The reference to the string "world" is passed by reference.
void Act(string h, ref string w)
{
    h += "!";
    w += "!";
    Console.WriteLine( $"{h} {w}"); // hello! world!
}

Console.WriteLine( $"{hello} {world}"); // hello world!
```

## String interpolation

A **string interpolation** is a feature in C# that allows to insert variables or expressions into string literals. This feature provides a concise way to create formatted strings, rather than concatenating multiple strings together.

```csharp
string name = "John";
string message = $"Hello {name}!";
Console.WriteLine(message); // Hello John!
```
