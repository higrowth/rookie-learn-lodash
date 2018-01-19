* <a href="#_addaugend-addend">`_.add`</a>
* <a href="#_ceilnumber-precision0">`_.ceil`</a>
* <a href="#_dividedividend-divisor">`_.divide`</a>
* <a href="#_floornumber-precision0">`_.floor`</a>
* <a href="#_maxarray">`_.max`</a>
* <a href="#_maxbyarray-iteratee_identity">`_.maxBy`</a>
* <a href="#_meanarray">`_.mean`</a>
* <a href="#_meanbyarray-iteratee_identity">`_.meanBy`</a>
* <a href="#_minarray">`_.min`</a>
* <a href="#_minbyarray-iteratee_identity">`_.minBy`</a>
* <a href="#_multiplymultiplier-multiplicand">`_.multiply`</a>
* <a href="#_roundnumber-precision0">`_.round`</a>
* <a href="#_subtractminuend-subtrahend">`_.subtract`</a>
* <a href="#_sumarray">`_.sum`</a>
* <a href="#_sumbyarray-iteratee_identity">`_.sumBy`</a>


## `“Math” Methods`

<!-- div -->

<h3 id="_addaugend-addend"><code>_.add(augend, addend)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16165 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.add "See the npm package") [&#x24C9;][1]

Adds two numbers.

#### Since
3.4.0

#### Arguments
1. `augend` *(number)*: The first number in an addition.
2. `addend` *(number)*: The second number in an addition.

#### Returns
*(number)*: Returns the total.

#### Example
```js
_.add(6, 4);
// => 10
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ceilnumber-precision0"><code>_.ceil(number, [precision=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16190 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.ceil "See the npm package") [&#x24C9;][1]

Computes `number` rounded up to `precision`.

#### Since
3.10.0

#### Arguments
1. `number` *(number)*: The number to round up.
2. `[precision=0]` *(number)*: The precision to round up to.

#### Returns
*(number)*: Returns the rounded up number.

#### Example
```js
_.ceil(4.006);
// => 5

_.ceil(6.004, 2);
// => 6.01

_.ceil(6040, -2);
// => 6100
```
---

<!-- /div -->

<!-- div -->

<h3 id="_dividedividend-divisor"><code>_.divide(dividend, divisor)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16207 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.divide "See the npm package") [&#x24C9;][1]

Divide two numbers.

#### Since
4.7.0

#### Arguments
1. `dividend` *(number)*: The first number in a division.
2. `divisor` *(number)*: The second number in a division.

#### Returns
*(number)*: Returns the quotient.

#### Example
```js
_.divide(6, 4);
// => 1.5
```
---

<!-- /div -->

<!-- div -->

<h3 id="_floornumber-precision0"><code>_.floor(number, [precision=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16232 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.floor "See the npm package") [&#x24C9;][1]

Computes `number` rounded down to `precision`.

#### Since
3.10.0

#### Arguments
1. `number` *(number)*: The number to round down.
2. `[precision=0]` *(number)*: The precision to round down to.

#### Returns
*(number)*: Returns the rounded down number.

#### Example
```js
_.floor(4.006);
// => 4

_.floor(0.046, 2);
// => 0.04

_.floor(4060, -2);
// => 4000
```
---

<!-- /div -->

<!-- div -->

<h3 id="_maxarray"><code>_.max(array)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16252 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.max "See the npm package") [&#x24C9;][1]

Computes the maximum value of `array`. If `array` is empty or falsey,
`undefined` is returned.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.

#### Returns
*(&#42;)*: Returns the maximum value.

#### Example
```js
_.max([4, 2, 8, 6]);
// => 8

_.max([]);
// => undefined
```
---

<!-- /div -->

<!-- div -->

<h3 id="_maxbyarray-iteratee_identity"><code>_.maxBy(array, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16281 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.maxby "See the npm package") [&#x24C9;][1]

This method is like `_.max` except that it accepts `iteratee` which is
invoked for each element in `array` to generate the criterion by which
the value is ranked. The iteratee is invoked with one argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(&#42;)*: Returns the maximum value.

#### Example
```js
var objects = [{ 'n': 1 }, { 'n': 2 }];

_.maxBy(objects, function(o) { return o.n; });
// => { 'n': 2 }

// The `_.property` iteratee shorthand.
_.maxBy(objects, 'n');
// => { 'n': 2 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_meanarray"><code>_.mean(array)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16301 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.mean "See the npm package") [&#x24C9;][1]

Computes the mean of the values in `array`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.

#### Returns
*(number)*: Returns the mean.

#### Example
```js
_.mean([4, 2, 8, 6]);
// => 5
```
---

<!-- /div -->

<!-- div -->

<h3 id="_meanbyarray-iteratee_identity"><code>_.meanBy(array, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16328 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.meanby "See the npm package") [&#x24C9;][1]

This method is like `_.mean` except that it accepts `iteratee` which is
invoked for each element in `array` to generate the value to be averaged.
The iteratee is invoked with one argument: *(value)*.

#### Since
4.7.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(number)*: Returns the mean.

#### Example
```js
var objects = [{ 'n': 4 }, { 'n': 2 }, { 'n': 8 }, { 'n': 6 }];

_.meanBy(objects, function(o) { return o.n; });
// => 5

// The `_.property` iteratee shorthand.
_.meanBy(objects, 'n');
// => 5
```
---

<!-- /div -->

<!-- div -->

<h3 id="_minarray"><code>_.min(array)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16350 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.min "See the npm package") [&#x24C9;][1]

Computes the minimum value of `array`. If `array` is empty or falsey,
`undefined` is returned.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.

#### Returns
*(&#42;)*: Returns the minimum value.

#### Example
```js
_.min([4, 2, 8, 6]);
// => 2

_.min([]);
// => undefined
```
---

<!-- /div -->

<!-- div -->

<h3 id="_minbyarray-iteratee_identity"><code>_.minBy(array, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16379 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.minby "See the npm package") [&#x24C9;][1]

This method is like `_.min` except that it accepts `iteratee` which is
invoked for each element in `array` to generate the criterion by which
the value is ranked. The iteratee is invoked with one argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(&#42;)*: Returns the minimum value.

#### Example
```js
var objects = [{ 'n': 1 }, { 'n': 2 }];

_.minBy(objects, function(o) { return o.n; });
// => { 'n': 1 }

// The `_.property` iteratee shorthand.
_.minBy(objects, 'n');
// => { 'n': 1 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_multiplymultiplier-multiplicand"><code>_.multiply(multiplier, multiplicand)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16400 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.multiply "See the npm package") [&#x24C9;][1]

Multiply two numbers.

#### Since
4.7.0

#### Arguments
1. `multiplier` *(number)*: The first number in a multiplication.
2. `multiplicand` *(number)*: The second number in a multiplication.

#### Returns
*(number)*: Returns the product.

#### Example
```js
_.multiply(6, 4);
// => 24
```
---

<!-- /div -->

<!-- div -->

<h3 id="_roundnumber-precision0"><code>_.round(number, [precision=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16425 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.round "See the npm package") [&#x24C9;][1]

Computes `number` rounded to `precision`.

#### Since
3.10.0

#### Arguments
1. `number` *(number)*: The number to round.
2. `[precision=0]` *(number)*: The precision to round to.

#### Returns
*(number)*: Returns the rounded number.

#### Example
```js
_.round(4.006);
// => 4

_.round(4.006, 2);
// => 4.01

_.round(4060, -2);
// => 4100
```
---

<!-- /div -->

<!-- div -->

<h3 id="_subtractminuend-subtrahend"><code>_.subtract(minuend, subtrahend)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16442 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.subtract "See the npm package") [&#x24C9;][1]

Subtract two numbers.

#### Since
4.0.0

#### Arguments
1. `minuend` *(number)*: The first number in a subtraction.
2. `subtrahend` *(number)*: The second number in a subtraction.

#### Returns
*(number)*: Returns the difference.

#### Example
```js
_.subtract(6, 4);
// => 2
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sumarray"><code>_.sum(array)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16460 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sum "See the npm package") [&#x24C9;][1]

Computes the sum of the values in `array`.

#### Since
3.4.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.

#### Returns
*(number)*: Returns the sum.

#### Example
```js
_.sum([4, 2, 8, 6]);
// => 20
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sumbyarray-iteratee_identity"><code>_.sumBy(array, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16489 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sumby "See the npm package") [&#x24C9;][1]

This method is like `_.sum` except that it accepts `iteratee` which is
invoked for each element in `array` to generate the value to be summed.
The iteratee is invoked with one argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(number)*: Returns the sum.

#### Example
```js
var objects = [{ 'n': 4 }, { 'n': 2 }, { 'n': 8 }, { 'n': 6 }];

_.sumBy(objects, function(o) { return o.n; });
// => 20

// The `_.property` iteratee shorthand.
_.sumBy(objects, 'n');
// => 20
```
---

<!-- /div -->

<!-- /div -->

<!-- div -->



