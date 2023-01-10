# Basic Types

For programs to be useful, we need to be able to work with some of the simplest units of data: numbers, strings, structures, boolean values, and the like. In TypeScript, we support the same types as you would expect in JavaScript, with an extra enumeration type thrown in to help things along.

### Boolean

The most basic datatype is the simple true/fals value, which JavaScript and TypeScript call a `boolean` value.

```ts
let isDone: boolean = false;
```

### Number

As in JavaScript, all numbers in TypeScript are either floating point values or BigIntgers. These floating point numbers get the type `number`, while BigIntergers get the type `bigint`. In addition to hexadecimal literals, TypeScript also supports binary and octal literals introduced in ECMAScript 2015.

```ts
let decimal: number =6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
let big: bigint = 100n;
```

### String

Another fundamental part of creating programs in JavaScript for webpages and servers alike is working with textual data. As in other languages, we use the type `string` to refer to these textual datatypes. Just like JavaScript, TypeScript also uses double quotes `(")` or single quotes `(')` to surround string data.

```ts
let color: string = "blue";
color = 'red';
```

You can also use template strings, which can span multiple lines and have embedded expressions. These strings are surrounded by the backtick/backquote ``(`)`` character, and embedded expresions are of the form `${ expr }`. 

```ts
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${fullName}.
I'll be ${age + 1} years old next month.`;
```

This is equivalent to declaring `sentence` like so:

```ts
let sentence: string =
    "Hello, my name is " +
    fullName +
    ".\n\n" +
    "I'll be " +
    (age + 1) +
    " years old next month.";
```

### Array

TypeScript, like JavaScript, allows you to work with arrays of values. Array types can be written in one of two ways. In the first, you use the type of the elements followed by `[]` to denote an array of that element type:

```ts
let list: number [] = [1, 2, 3];
```

The second way uses a generic array type, `Array<elemType>`:

```ts
let list: Array<number> = [1, 2, 3];
```

### Tuple

Tuple types allow you to express an array with a fixed number of elements whose types are known, but need not be the same. For example, you may want to represent a value as a pair of a `string` and a `number`:

```ts
// Declare a tuple type
let x: [string, number];
// Initialize it
x = ["hello", 10]; // OK
// Initialize it incorrectly
x = [10, "hello"]; // Error.
Type 'number' is not assignable to type 'string'.
Type 'string' is not assignable to type 'number'.
```

When accessing an element with a known index, the correct type is retrieved:

```ts
// OK
console.log(x[0].substring(1));

console.log(x[1].substring(1));
Property 'substring' does not exist on type 'number'.
```

Accessing an element outside the set of known indices fails with an error:

```ts
x[3] = "world";
Tuple type '[string, number]' of length '2' has no element at index '3'.

console.log(x[5].toString());
Object is possibly 'underfined'.
Tuple type '[string, number]' of length '2' has no element at index '5'.
```

### Enum

A helpful addition to the standard set of datatypes from JavaScript is the `enum`. As in languages like C#, an enum is a way of giving move friendly names to sets of numeric values.

```ts
enum Color {
    Red,
    Green,
    Blue,
}
let c: Color = Color.Green;
```

By default, enums begin numbering their members starting at 0. You can change this by manually setting the value of one of its members. For example, we can start the previous exmaple at `1` instead of `0`:

```ts
enum Color {
    Red = 1,
    Green,
    Blue,
}
let c: Color = Color.Green;
```

Or even manually set all the values in the enum:

```ts
enum Color {
    Red = 1,
    Green = 2,
    Blue = 4,
}
let c: Color = Color.Green;
```

A handy feature of enums is that you can also go from a numeric value to the name of that value in the enum. For example, if we had the value `2` but weren't sure what that mapped to in the `Color` enum above, we could look up the corresponding name:

```ts
enum Color{
    Red = 1,
    Green,
    Blue,
}
let colorName: string = Color[2];

// Displays 'Green'
console.log(colorName);
```
