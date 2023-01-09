# Basic Types

For programs to be useful, we need to be able to work with some of the simplest units of data: numbers, strings, structures, boolean values, and the like. In TypeScript, we support the same types as you would expect in JavaScript, with an extra enumeration type thrown in to help things along.

### Boolean

The most basic datatype is the simple true/fals value, which JavaScript and TypeScript call a `boolean` value.

- `let isDone: boolean = false;`

### Number

As in JavaScript, all numbers in TypeScript are either floating point values or BigIntgers. These floating point numbers get the type `number`, while BigIntergers get the type `bigint`. In addition to hexadecimal literals, TypeScript also supports binary and octal literals introduced in ECMAScript 2015.

- `let decimal: number =6;`
- `let hex: number = 0xf00d;`
- `let binary: number = 0b1010;`
- `let octal: number = 0o744;`
- `let big: bigint = 100n;`

### String

Another fundamental part of creating programs in JavaScript for webpages and servers alike is working with textual data. As in other languages, we use the type `string` to refer to these textual datatypes. Just like JavaScript, TypeScript also uses double quotes `(")` or single quotes `(')` to surround string data.

- `let color: string = "blue";`
- `color = 'red';`

You can also use template strings, which can span multiple lines and have embedded expressions. These strings are surrounded by the backtick/backquote ``(`)`` character, and embedded expresions are of the form `${ expr }`. 

- ``let fullName: string = `Bob Bobbington`;``
- `let age: number = 37;`
- ```let sentence: string = `Hello, my name is ${fullName}.```
- ``I'll be ${age + 1} years old next month.`;``

This is equivalent to declaring `sectence` like so:

`let sentence: string =`
   - `"Hello, my name is " +`
   - `fullName +`
   - `".\n\n" +`
   - `"I'll be " +`
   - `(age + 1) +`
   - `" years old next month.";`

### Array

TypeScript, like JavaScript, allows you to work with arrays of values. Array types can be written in one of two ways. In the first, you use the type of the elements followed by `[]` to denote an array of that element type:

```
`let list: number [] = [1, 2, 3];`
```

The second way uses a generic array type, `Array<elemType>`:

```
`let list: Array<number> = [1, 2, 3];`
```
