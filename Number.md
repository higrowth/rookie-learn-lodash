* <a href="#_clampnumber-lower-upper">`_.clamp`</a>
* <a href="#_inrangenumber-start0-end">`_.inRange`</a>
* <a href="#_randomlower0-upper1-floating">`_.random`</a>


## `“Number” Methods`

<!-- div -->

<h3 id="_clampnumber-lower-upper"><code>_.clamp(number, [lower], upper)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L13959 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.clamp "See the npm package") [&#x24C9;][1]

Clamps `number` within the inclusive `lower` and `upper` bounds.

#### Since
4.0.0

#### Arguments
1. `number` *(number)*: The number to clamp.
2. `[lower]` *(number)*: The lower bound.
3. `upper` *(number)*: The upper bound.

#### Returns
*(number)*: Returns the clamped number.

#### Example
```js
_.clamp(-10, -5, 5);
// => -5

_.clamp(10, -5, 5);
// => 5
```
---

<!-- /div -->

<!-- div -->

<h3 id="_inrangenumber-start0-end"><code>_.inRange(number, [start=0], end)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14013 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.inrange "See the npm package") [&#x24C9;][1]

Checks if `n` is between `start` and up to, but not including, `end`. If
`end` is not specified, it's set to `start` with `start` then set to `0`.
If `start` is greater than `end` the params are swapped to support
negative ranges.

#### Since
3.3.0

#### Arguments
1. `number` *(number)*: The number to check.
2. `[start=0]` *(number)*: The start of the range.
3. `end` *(number)*: The end of the range.

#### Returns
*(boolean)*: Returns `true` if `number` is in the range, else `false`.

#### Example
```js
_.inRange(3, 2, 4);
// => true

_.inRange(4, 8);
// => true

_.inRange(4, 2);
// => false

_.inRange(2, 2);
// => false

_.inRange(1.2, 2);
// => true

_.inRange(5.2, 4);
// => false

_.inRange(-3, -2, -6);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_randomlower0-upper1-floating"><code>_.random([lower=0], [upper=1], [floating])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14056 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.random "See the npm package") [&#x24C9;][1]

Produces a random number between the inclusive `lower` and `upper` bounds.
If only one argument is provided a number between `0` and the given number
is returned. If `floating` is `true`, or either `lower` or `upper` are
floats, a floating-point number is returned instead of an integer.
<br>
<br>
**Note:** JavaScript follows the IEEE-754 standard for resolving
floating-point values which can produce unexpected results.

#### Since
0.7.0

#### Arguments
1. `[lower=0]` *(number)*: The lower bound.
2. `[upper=1]` *(number)*: The upper bound.
3. `[floating]` *(boolean)*: Specify returning a floating-point number.

#### Returns
*(number)*: Returns the random number.

#### Example
```js
_.random(0, 5);
// => an integer between 0 and 5

_.random(5);
// => also an integer between 0 and 5

_.random(5, true);
// => a floating-point number between 0 and 5

_.random(1.2, 5.2);
// => a floating-point number between 1.2 and 5.2
```
---

<!-- /div -->

<!-- /div -->

<!-- div -->