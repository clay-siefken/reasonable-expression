# Reasonable Expression

Make working with math expressions in js less painful.

```js
// Math expressions have a distinct structure.
// A = P(1+r/n)^nt

// Javascript is aware of this, and models its own
// math handling in a vaguely similar way.
// However, JS floating points are dangerous.

let A = P * Math.pow(1 + r / n, n * t); // don't do it

// Other libraries handle this quite well.
// Decimal JS is a very lightweight library that one might choose to use.
// The usability of these functions leave much to be desired...

let A = calculate(P).mul(calculate(1).add(calculate(r).div(n)).pow(calculate(n).mul(t))); 

// The intent of this library is to provide a simple means
// of working with decimalJS functions without losing the clarity
// of a math-like syntax.

let A = evaluate(`${P} * pow(1 + ${r} / ${n}, ${n} * ${t})`); 

// ... or ...

let A = evaluate(`P * pow(1 + r / n, n * t)`, {P, r, n, t }); 

```

Some other constraints in this work:
- Must be very small, no outside libraries.
- No use of async/await/Promises.
