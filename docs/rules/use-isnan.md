# Require isNaN() (use-isnan)

In JavaScript, `NaN` is a special value of the `Number` type. It's used to represent any of the "not-a-number" values represented by the double-precision 64-bit format as specified by the IEEE Standard for Binary Floating-Point Arithmetic. `NaN` has the unique property of not being equal to anything, including itself. That is to say, that the condition `NaN !== NaN` evaluates to true.

## Rule Details

This rule is aimed at eliminating potential errors as the result of comparing against the special value `NaN`.

The following patterns are considered warnings:

```js
if (foo == NaN) {
	// ...
}

if (foo != NaN) {
	// ...
}
```

The following patterns are not warnings:

```js
if (isNaN(foo)) {
	// ...
}

if (isNaN(NaN)) {
	// ...
}
```

## Further reading

 - [Use the isNaN function to compare with NaN](http://jslinterrors.com/use-the-isnan-function-to-compare-with-nan/)
