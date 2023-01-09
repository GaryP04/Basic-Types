# Basic Types

Boolean

The most basic datatype is the simple true/fals value, which JavaScript and TypeScript call a 'boolean' value.

let isDone: boolean = false;

Number

As in JavaScript, all numbers in TypeScript are either floating point values or BigIntgers. These floating point numbers get the type 'number', while BigIntergers get the type 'bitint'. In addition to hexadecimal literals, TypeScript also supports binary and octal literals introduced in ECMAScript 2015.

let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
let big: bigint = 100n;

