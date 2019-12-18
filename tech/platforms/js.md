# JavaScript

## Arrays

- `push` - add to end
- `pop` - remove from end (Stack like)
- `shift` - dequeue; remove from beginning (Queue like)
- `unshift` - insert in beginning

## Slice, Splice and Split

- https://www.freecodecamp.org/news/lets-clear-up-the-confusion-around-the-slice-splice-split-methods-in-javascript-8ba3266c29ae/

- https://stackoverflow.com/questions/2243824/what-is-the-difference-between-string-slice-and-string-substring - `substring` is similar to `slice` for string with a few changes for negative indexes (i.e, doesn't follow the slice logic of counting from the end, and instead taken a 0)

- `substr` is `start, len`, while others are `start, end`

## Tricks

- `!!val` - Double negate to coerce false values (0, null and undefined, etc), and return boolean
- `10.7 | 0` - `Math.trunc(10.7)`
- `~~10.7` - `Math.trunc(10.7)`

```js
Math.trunc(13.37)   // 13
Math.trunc(42.84)   // 42
Math.trunc(0.123)   //  0
Math.trunc(-0.123)  // -0
Math.trunc("-1.123")// -1
Math.trunc(NaN)     // NaN
Math.trunc("foo")   // NaN
Math.trunc()        // NaN
```

```js
Math.floor(13.37)   // 13
Math.floor(42.84)   // 42
Math.floor(0.123)   //  0
Math.floor(-0.123)  // -1
Math.floor("-1.123")// -2
Math.floor(NaN)     // NaN
Math.floor("foo")   // NaN
Math.floor()        // NaN
```

```js
~~13.37     // 13
~~42.84     // 42
~~0.123     // 0
~~-0.123    // 0
~~"-1.123"  // -1
~~NaN       // 0
~~"foo"     // 0
~~undefined // 0
```

```js
13.37 | 0     // 13
42.84 | 0     // 42
0.123 | 0     // 0
-0.123 | 0    // 0
"-1.123" | 0  // -1
NaN | 0       // 0
"foo" | 0     // 0
undefined | 0 // 0
```

## Quirks

- All bit ops convert number to `i32` before op, except `>>>` which does to `u32`.
- `(x >>> 0).toString(2)` - `>>>` - Logical bitshift does `u32`, so it gives the actual binary repr instead of literal `-(0b of x)`

### References

- https://kangax.github.io/compat-table/es2016plus/
- https://stackoverflow.com/questions/7487977/using-bitwise-or-0-to-floor-a-number
