* <a href="#_castarrayvalue">`_.castArray`</a>
* <a href="#_clonevalue">`_.clone`</a>
* <a href="#_clonedeepvalue">`_.cloneDeep`</a>
* <a href="#_clonedeepwithvalue-customizer">`_.cloneDeepWith`</a>
* <a href="#_clonewithvalue-customizer">`_.cloneWith`</a>
* <a href="#_conformstoobject-source">`_.conformsTo`</a>
* <a href="#_eqvalue-other">`_.eq`</a>
* <a href="#_gtvalue-other">`_.gt`</a>
* <a href="#_gtevalue-other">`_.gte`</a>
* <a href="#_isargumentsvalue">`_.isArguments`</a>
* <a href="#_isarrayvalue">`_.isArray`</a>
* <a href="#_isarraybuffervalue">`_.isArrayBuffer`</a>
* <a href="#_isarraylikevalue">`_.isArrayLike`</a>
* <a href="#_isarraylikeobjectvalue">`_.isArrayLikeObject`</a>
* <a href="#_isbooleanvalue">`_.isBoolean`</a>
* <a href="#_isbuffervalue">`_.isBuffer`</a>
* <a href="#_isdatevalue">`_.isDate`</a>
* <a href="#_iselementvalue">`_.isElement`</a>
* <a href="#_isemptyvalue">`_.isEmpty`</a>
* <a href="#_isequalvalue-other">`_.isEqual`</a>
* <a href="#_isequalwithvalue-other-customizer">`_.isEqualWith`</a>
* <a href="#_iserrorvalue">`_.isError`</a>
* <a href="#_isfinitevalue">`_.isFinite`</a>
* <a href="#_isfunctionvalue">`_.isFunction`</a>
* <a href="#_isintegervalue">`_.isInteger`</a>
* <a href="#_islengthvalue">`_.isLength`</a>
* <a href="#_ismapvalue">`_.isMap`</a>
* <a href="#_ismatchobject-source">`_.isMatch`</a>
* <a href="#_ismatchwithobject-source-customizer">`_.isMatchWith`</a>
* <a href="#_isnanvalue">`_.isNaN`</a>
* <a href="#_isnativevalue">`_.isNative`</a>
* <a href="#_isnilvalue">`_.isNil`</a>
* <a href="#_isnullvalue">`_.isNull`</a>
* <a href="#_isnumbervalue">`_.isNumber`</a>
* <a href="#_isobjectvalue">`_.isObject`</a>
* <a href="#_isobjectlikevalue">`_.isObjectLike`</a>
* <a href="#_isplainobjectvalue">`_.isPlainObject`</a>
* <a href="#_isregexpvalue">`_.isRegExp`</a>
* <a href="#_issafeintegervalue">`_.isSafeInteger`</a>
* <a href="#_issetvalue">`_.isSet`</a>
* <a href="#_isstringvalue">`_.isString`</a>
* <a href="#_issymbolvalue">`_.isSymbol`</a>
* <a href="#_istypedarrayvalue">`_.isTypedArray`</a>
* <a href="#_isundefinedvalue">`_.isUndefined`</a>
* <a href="#_isweakmapvalue">`_.isWeakMap`</a>
* <a href="#_isweaksetvalue">`_.isWeakSet`</a>
* <a href="#_ltvalue-other">`_.lt`</a>
* <a href="#_ltevalue-other">`_.lte`</a>
* <a href="#_toarrayvalue">`_.toArray`</a>
* <a href="#_tofinitevalue">`_.toFinite`</a>
* <a href="#_tointegervalue">`_.toInteger`</a>
* <a href="#_tolengthvalue">`_.toLength`</a>
* <a href="#_tonumbervalue">`_.toNumber`</a>
* <a href="#_toplainobjectvalue">`_.toPlainObject`</a>
* <a href="#_tosafeintegervalue">`_.toSafeInteger`</a>
* <a href="#_tostringvalue">`_.toString`</a>




## `“Lang” Methods`

<!-- div -->

<h3 id="_castarrayvalue"><code>_.castArray(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11009 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.castarray "See the npm package") [&#x24C9;][1]

Casts `value` as an array if it's not one.

#### Since
4.4.0

#### Arguments
1. `value` *(&#42;)*: The value to inspect.

#### Returns
*(Array)*: Returns the cast array.

#### Example
```js
_.castArray(1);
// => [1]

_.castArray({ 'a': 1 });
// => [{ 'a': 1 }]

_.castArray('abc');
// => ['abc']

_.castArray(null);
// => [null]

_.castArray(undefined);
// => [undefined]

_.castArray();
// => []

var array = [1, 2, 3];
console.log(_.castArray(array) === array);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_clonevalue"><code>_.clone(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11043 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.clone "See the npm package") [&#x24C9;][1]

Creates a shallow clone of `value`.
<br>
<br>
**Note:** This method is loosely based on the
[structured clone algorithm](https://mdn.io/Structured_clone_algorithm)
and supports cloning arrays, array buffers, booleans, date objects, maps,
numbers, `Object` objects, regexes, sets, strings, symbols, and typed
arrays. The own enumerable properties of `arguments` objects are cloned
as plain objects. An empty object is returned for uncloneable values such
as error objects, functions, DOM nodes, and WeakMaps.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to clone.

#### Returns
*(&#42;)*: Returns the cloned value.

#### Example
```js
var objects = [{ 'a': 1 }, { 'b': 2 }];

var shallow = _.clone(objects);
console.log(shallow[0] === objects[0]);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_clonedeepvalue"><code>_.cloneDeep(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11101 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.clonedeep "See the npm package") [&#x24C9;][1]

This method is like `_.clone` except that it recursively clones `value`.

#### Since
1.0.0

#### Arguments
1. `value` *(&#42;)*: The value to recursively clone.

#### Returns
*(&#42;)*: Returns the deep cloned value.

#### Example
```js
var objects = [{ 'a': 1 }, { 'b': 2 }];

var deep = _.cloneDeep(objects);
console.log(deep[0] === objects[0]);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_clonedeepwithvalue-customizer"><code>_.cloneDeepWith(value, [customizer])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11133 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.clonedeepwith "See the npm package") [&#x24C9;][1]

This method is like `_.cloneWith` except that it recursively clones `value`.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to recursively clone.
2. `[customizer]` *(Function)*: The function to customize cloning.

#### Returns
*(&#42;)*: Returns the deep cloned value.

#### Example
```js
function customizer(value) {
  if (_.isElement(value)) {
    return value.cloneNode(true);
  }
}

var el = _.cloneDeepWith(document.body, customizer);

console.log(el === document.body);
// => false
console.log(el.nodeName);
// => 'BODY'
console.log(el.childNodes.length);
// => 20
```
---

<!-- /div -->

<!-- div -->

<h3 id="_clonewithvalue-customizer"><code>_.cloneWith(value, [customizer])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11078 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.clonewith "See the npm package") [&#x24C9;][1]

This method is like `_.clone` except that it accepts `customizer` which
is invoked to produce the cloned value. If `customizer` returns `undefined`,
cloning is handled by the method instead. The `customizer` is invoked with
up to four arguments; *(value [, index|key, object, stack])*.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to clone.
2. `[customizer]` *(Function)*: The function to customize cloning.

#### Returns
*(&#42;)*: Returns the cloned value.

#### Example
```js
function customizer(value) {
  if (_.isElement(value)) {
    return value.cloneNode(false);
  }
}

var el = _.cloneWith(document.body, customizer);

console.log(el === document.body);
// => false
console.log(el.nodeName);
// => 'BODY'
console.log(el.childNodes.length);
// => 0
```
---

<!-- /div -->

<!-- div -->

<h3 id="_conformstoobject-source"><code>_.conformsTo(object, source)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11162 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.conformsto "See the npm package") [&#x24C9;][1]

Checks if `object` conforms to `source` by invoking the predicate
properties of `source` with the corresponding property values of `object`.
<br>
<br>
**Note:** This method is equivalent to `_.conforms` when `source` is
partially applied.

#### Since
4.14.0

#### Arguments
1. `object` *(Object)*: The object to inspect.
2. `source` *(Object)*: The object of property predicates to conform to.

#### Returns
*(boolean)*: Returns `true` if `object` conforms, else `false`.

#### Example
```js
var object = { 'a': 1, 'b': 2 };

_.conformsTo(object, { 'b': function(n) { return n > 1; } });
// => true

_.conformsTo(object, { 'b': function(n) { return n > 2; } });
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_eqvalue-other"><code>_.eq(value, other)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11198 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.eq "See the npm package") [&#x24C9;][1]

Performs a
[`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
comparison between two values to determine if they are equivalent.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.

#### Returns
*(boolean)*: Returns `true` if the values are equivalent, else `false`.

#### Example
```js
var object = { 'a': 1 };
var other = { 'a': 1 };

_.eq(object, object);
// => true

_.eq(object, other);
// => false

_.eq('a', 'a');
// => true

_.eq('a', Object('a'));
// => false

_.eq(NaN, NaN);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_gtvalue-other"><code>_.gt(value, other)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11225 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.gt "See the npm package") [&#x24C9;][1]

Checks if `value` is greater than `other`.

#### Since
3.9.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.

#### Returns
*(boolean)*: Returns `true` if `value` is greater than `other`, else `false`.

#### Example
```js
_.gt(3, 1);
// => true

_.gt(3, 3);
// => false

_.gt(1, 3);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_gtevalue-other"><code>_.gte(value, other)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11250 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.gte "See the npm package") [&#x24C9;][1]

Checks if `value` is greater than or equal to `other`.

#### Since
3.9.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.

#### Returns
*(boolean)*: Returns `true` if `value` is greater than or equal to `other`, else `false`.

#### Example
```js
_.gte(3, 1);
// => true

_.gte(3, 3);
// => true

_.gte(1, 3);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isargumentsvalue"><code>_.isArguments(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11272 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isarguments "See the npm package") [&#x24C9;][1]

Checks if `value` is likely an `arguments` object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an `arguments` object, else `false`.

#### Example
```js
_.isArguments(function() { return arguments; }());
// => true

_.isArguments([1, 2, 3]);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isarrayvalue"><code>_.isArray(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11300 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isarray "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as an `Array` object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an array, else `false`.

#### Example
```js
_.isArray([1, 2, 3]);
// => true

_.isArray(document.body.children);
// => false

_.isArray('abc');
// => false

_.isArray(_.noop);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isarraybuffervalue"><code>_.isArrayBuffer(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11319 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isarraybuffer "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as an `ArrayBuffer` object.

#### Since
4.3.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an array buffer, else `false`.

#### Example
```js
_.isArrayBuffer(new ArrayBuffer(2));
// => true

_.isArrayBuffer(new Array(2));
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isarraylikevalue"><code>_.isArrayLike(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11346 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isarraylike "See the npm package") [&#x24C9;][1]

Checks if `value` is array-like. A value is considered array-like if it's
not a function and has a `value.length` that's an integer greater than or
equal to `0` and less than or equal to `Number.MAX_SAFE_INTEGER`.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is array-like, else `false`.

#### Example
```js
_.isArrayLike([1, 2, 3]);
// => true

_.isArrayLike(document.body.children);
// => true

_.isArrayLike('abc');
// => true

_.isArrayLike(_.noop);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isarraylikeobjectvalue"><code>_.isArrayLikeObject(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11375 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isarraylikeobject "See the npm package") [&#x24C9;][1]

This method is like `_.isArrayLike` except that it also checks if `value`
is an object.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an array-like object, else `false`.

#### Example
```js
_.isArrayLikeObject([1, 2, 3]);
// => true

_.isArrayLikeObject(document.body.children);
// => true

_.isArrayLikeObject('abc');
// => false

_.isArrayLikeObject(_.noop);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isbooleanvalue"><code>_.isBoolean(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11396 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isboolean "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a boolean primitive or object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a boolean, else `false`.

#### Example
```js
_.isBoolean(false);
// => true

_.isBoolean(null);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isbuffervalue"><code>_.isBuffer(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11418 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isbuffer "See the npm package") [&#x24C9;][1]

Checks if `value` is a buffer.

#### Since
4.3.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a buffer, else `false`.

#### Example
```js
_.isBuffer(new Buffer(2));
// => true

_.isBuffer(new Uint8Array(2));
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isdatevalue"><code>_.isDate(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11437 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isdate "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `Date` object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a date object, else `false`.

#### Example
```js
_.isDate(new Date);
// => true

_.isDate('Mon April 23 2012');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_iselementvalue"><code>_.isElement(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11456 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.iselement "See the npm package") [&#x24C9;][1]

Checks if `value` is likely a DOM element.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a DOM element, else `false`.

#### Example
```js
_.isElement(document.body);
// => true

_.isElement('<body>');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isemptyvalue"><code>_.isEmpty(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11493 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isempty "See the npm package") [&#x24C9;][1]

Checks if `value` is an empty object, collection, map, or set.
<br>
<br>
Objects are considered empty if they have no own enumerable string keyed
properties.
<br>
<br>
Array-like values such as `arguments` objects, arrays, buffers, strings, or
jQuery-like collections are considered empty if they have a `length` of `0`.
Similarly, maps and sets are considered empty if they have a `size` of `0`.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is empty, else `false`.

#### Example
```js
_.isEmpty(null);
// => true

_.isEmpty(true);
// => true

_.isEmpty(1);
// => true

_.isEmpty([1, 2, 3]);
// => false

_.isEmpty({ 'a': 1 });
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isequalvalue-other"><code>_.isEqual(value, other)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11545 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isequal "See the npm package") [&#x24C9;][1]

Performs a deep comparison between two values to determine if they are
equivalent.
<br>
<br>
**Note:** This method supports comparing arrays, array buffers, booleans,
date objects, error objects, maps, numbers, `Object` objects, regexes,
sets, strings, symbols, and typed arrays. `Object` objects are compared
by their own, not inherited, enumerable properties. Functions and DOM
nodes are compared by strict equality, i.e. `===`.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.

#### Returns
*(boolean)*: Returns `true` if the values are equivalent, else `false`.

#### Example
```js
var object = { 'a': 1 };
var other = { 'a': 1 };

_.isEqual(object, other);
// => true

object === other;
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isequalwithvalue-other-customizer"><code>_.isEqualWith(value, other, [customizer])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11581 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isequalwith "See the npm package") [&#x24C9;][1]

This method is like `_.isEqual` except that it accepts `customizer` which
is invoked to compare values. If `customizer` returns `undefined`, comparisons
are handled by the method instead. The `customizer` is invoked with up to
six arguments: *(objValue, othValue [, index|key, object, other, stack])*.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.
3. `[customizer]` *(Function)*: The function to customize comparisons.

#### Returns
*(boolean)*: Returns `true` if the values are equivalent, else `false`.

#### Example
```js
function isGreeting(value) {
  return /^h(?:i|ello)$/.test(value);
}

function customizer(objValue, othValue) {
  if (isGreeting(objValue) && isGreeting(othValue)) {
    return true;
  }
}

var array = ['hello', 'goodbye'];
var other = ['hi', 'goodbye'];

_.isEqualWith(array, other, customizer);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_iserrorvalue"><code>_.isError(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11605 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.iserror "See the npm package") [&#x24C9;][1]

Checks if `value` is an `Error`, `EvalError`, `RangeError`, `ReferenceError`,
`SyntaxError`, `TypeError`, or `URIError` object.

#### Since
3.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an error object, else `false`.

#### Example
```js
_.isError(new Error);
// => true

_.isError(Error);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isfinitevalue"><code>_.isFinite(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11640 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isfinite "See the npm package") [&#x24C9;][1]

Checks if `value` is a finite primitive number.
<br>
<br>
**Note:** This method is based on
[`Number.isFinite`](https://mdn.io/Number/isFinite).

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a finite number, else `false`.

#### Example
```js
_.isFinite(3);
// => true

_.isFinite(Number.MIN_VALUE);
// => true

_.isFinite(Infinity);
// => false

_.isFinite('3');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isfunctionvalue"><code>_.isFunction(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11661 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isfunction "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `Function` object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a function, else `false`.

#### Example
```js
_.isFunction(_);
// => true

_.isFunction(/abc/);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isintegervalue"><code>_.isInteger(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11697 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isinteger "See the npm package") [&#x24C9;][1]

Checks if `value` is an integer.
<br>
<br>
**Note:** This method is based on
[`Number.isInteger`](https://mdn.io/Number/isInteger).

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an integer, else `false`.

#### Example
```js
_.isInteger(3);
// => true

_.isInteger(Number.MIN_VALUE);
// => false

_.isInteger(Infinity);
// => false

_.isInteger('3');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_islengthvalue"><code>_.isLength(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11727 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.islength "See the npm package") [&#x24C9;][1]

Checks if `value` is a valid array-like length.
<br>
<br>
**Note:** This method is loosely based on
[`ToLength`](http://ecma-international.org/ecma-262/7.0/#sec-tolength).

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a valid length, else `false`.

#### Example
```js
_.isLength(3);
// => true

_.isLength(Number.MIN_VALUE);
// => false

_.isLength(Infinity);
// => false

_.isLength('3');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ismapvalue"><code>_.isMap(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11807 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.ismap "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `Map` object.

#### Since
4.3.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a map, else `false`.

#### Example
```js
_.isMap(new Map);
// => true

_.isMap(new WeakMap);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ismatchobject-source"><code>_.isMatch(object, source)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11837 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.ismatch "See the npm package") [&#x24C9;][1]

Performs a partial deep comparison between `object` and `source` to
determine if `object` contains equivalent property values.
<br>
<br>
**Note:** This method is equivalent to `_.matches` when `source` is
partially applied.
<br>
<br>
Partial comparisons will match empty array and empty object `source`
values against any array or object value, respectively. See `_.isEqual`
for a list of supported value comparisons.

#### Since
3.0.0

#### Arguments
1. `object` *(Object)*: The object to inspect.
2. `source` *(Object)*: The object of property values to match.

#### Returns
*(boolean)*: Returns `true` if `object` is a match, else `false`.

#### Example
```js
var object = { 'a': 1, 'b': 2 };

_.isMatch(object, { 'b': 2 });
// => true

_.isMatch(object, { 'b': 1 });
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ismatchwithobject-source-customizer"><code>_.isMatchWith(object, source, [customizer])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11873 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.ismatchwith "See the npm package") [&#x24C9;][1]

This method is like `_.isMatch` except that it accepts `customizer` which
is invoked to compare values. If `customizer` returns `undefined`, comparisons
are handled by the method instead. The `customizer` is invoked with five
arguments: *(objValue, srcValue, index|key, object, source)*.

#### Since
4.0.0

#### Arguments
1. `object` *(Object)*: The object to inspect.
2. `source` *(Object)*: The object of property values to match.
3. `[customizer]` *(Function)*: The function to customize comparisons.

#### Returns
*(boolean)*: Returns `true` if `object` is a match, else `false`.

#### Example
```js
function isGreeting(value) {
  return /^h(?:i|ello)$/.test(value);
}

function customizer(objValue, srcValue) {
  if (isGreeting(objValue) && isGreeting(srcValue)) {
    return true;
  }
}

var object = { 'greeting': 'hello' };
var source = { 'greeting': 'hi' };

_.isMatchWith(object, source, customizer);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isnanvalue"><code>_.isNaN(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11906 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isnan "See the npm package") [&#x24C9;][1]

Checks if `value` is `NaN`.
<br>
<br>
**Note:** This method is based on
[`Number.isNaN`](https://mdn.io/Number/isNaN) and is not the same as
global [`isNaN`](https://mdn.io/isNaN) which returns `true` for
`undefined` and other non-number values.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is `NaN`, else `false`.

#### Example
```js
_.isNaN(NaN);
// => true

_.isNaN(new Number(NaN));
// => true

isNaN(undefined);
// => true

_.isNaN(undefined);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isnativevalue"><code>_.isNative(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11939 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isnative "See the npm package") [&#x24C9;][1]

Checks if `value` is a pristine native function.
<br>
<br>
**Note:** This method can't reliably detect native functions in the presence
of the core-js package because core-js circumvents this kind of detection.
Despite multiple requests, the core-js maintainer has made it clear: any
attempt to fix the detection will be obstructed. As a result, we're left
with little choice but to throw an error. Unfortunately, this also affects
packages, like [babel-polyfill](https://www.npmjs.com/package/babel-polyfill),
which rely on core-js.

#### Since
3.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a native function, else `false`.

#### Example
```js
_.isNative(Array.prototype.push);
// => true

_.isNative(_);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isnilvalue"><code>_.isNil(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11987 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isnil "See the npm package") [&#x24C9;][1]

Checks if `value` is `null` or `undefined`.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is nullish, else `false`.

#### Example
```js
_.isNil(null);
// => true

_.isNil(void 0);
// => true

_.isNil(NaN);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isnullvalue"><code>_.isNull(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11963 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isnull "See the npm package") [&#x24C9;][1]

Checks if `value` is `null`.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is `null`, else `false`.

#### Example
```js
_.isNull(null);
// => true

_.isNull(void 0);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isnumbervalue"><code>_.isNumber(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12017 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isnumber "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `Number` primitive or object.
<br>
<br>
**Note:** To exclude `Infinity`, `-Infinity`, and `NaN`, which are
classified as numbers, use the `_.isFinite` method.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a number, else `false`.

#### Example
```js
_.isNumber(3);
// => true

_.isNumber(Number.MIN_VALUE);
// => true

_.isNumber(Infinity);
// => true

_.isNumber('3');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isobjectvalue"><code>_.isObject(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11757 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isobject "See the npm package") [&#x24C9;][1]

Checks if `value` is the
[language type](http://www.ecma-international.org/ecma-262/7.0/#sec-ecmascript-language-types)
of `Object`. *(e.g. arrays, functions, objects, regexes, `new Number(0)`, and `new String('')`)*

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is an object, else `false`.

#### Example
```js
_.isObject({});
// => true

_.isObject([1, 2, 3]);
// => true

_.isObject(_.noop);
// => true

_.isObject(null);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isobjectlikevalue"><code>_.isObjectLike(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L11786 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isobjectlike "See the npm package") [&#x24C9;][1]

Checks if `value` is object-like. A value is object-like if it's not `null`
and has a `typeof` result of "object".

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is object-like, else `false`.

#### Example
```js
_.isObjectLike({});
// => true

_.isObjectLike([1, 2, 3]);
// => true

_.isObjectLike(_.noop);
// => false

_.isObjectLike(null);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isplainobjectvalue"><code>_.isPlainObject(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12050 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isplainobject "See the npm package") [&#x24C9;][1]

Checks if `value` is a plain object, that is, an object created by the
`Object` constructor or one with a `[[Prototype]]` of `null`.

#### Since
0.8.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a plain object, else `false`.

#### Example
```js
function Foo() {
  this.a = 1;
}

_.isPlainObject(new Foo);
// => false

_.isPlainObject([1, 2, 3]);
// => false

_.isPlainObject({ 'x': 0, 'y': 0 });
// => true

_.isPlainObject(Object.create(null));
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isregexpvalue"><code>_.isRegExp(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12080 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isregexp "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `RegExp` object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a regexp, else `false`.

#### Example
```js
_.isRegExp(/abc/);
// => true

_.isRegExp('/abc/');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_issafeintegervalue"><code>_.isSafeInteger(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12109 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.issafeinteger "See the npm package") [&#x24C9;][1]

Checks if `value` is a safe integer. An integer is safe if it's an IEEE-754
double precision number which isn't the result of a rounded unsafe integer.
<br>
<br>
**Note:** This method is based on
[`Number.isSafeInteger`](https://mdn.io/Number/isSafeInteger).

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a safe integer, else `false`.

#### Example
```js
_.isSafeInteger(3);
// => true

_.isSafeInteger(Number.MIN_VALUE);
// => false

_.isSafeInteger(Infinity);
// => false

_.isSafeInteger('3');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_issetvalue"><code>_.isSet(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12130 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isset "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `Set` object.

#### Since
4.3.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a set, else `false`.

#### Example
```js
_.isSet(new Set);
// => true

_.isSet(new WeakSet);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isstringvalue"><code>_.isString(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12149 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isstring "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `String` primitive or object.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a string, else `false`.

#### Example
```js
_.isString('abc');
// => true

_.isString(1);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_issymbolvalue"><code>_.isSymbol(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12171 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.issymbol "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `Symbol` primitive or object.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a symbol, else `false`.

#### Example
```js
_.isSymbol(Symbol.iterator);
// => true

_.isSymbol('abc');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_istypedarrayvalue"><code>_.isTypedArray(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12193 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.istypedarray "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a typed array.

#### Since
3.0.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a typed array, else `false`.

#### Example
```js
_.isTypedArray(new Uint8Array);
// => true

_.isTypedArray([]);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isundefinedvalue"><code>_.isUndefined(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12212 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isundefined "See the npm package") [&#x24C9;][1]

Checks if `value` is `undefined`.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is `undefined`, else `false`.

#### Example
```js
_.isUndefined(void 0);
// => true

_.isUndefined(null);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isweakmapvalue"><code>_.isWeakMap(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12233 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isweakmap "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `WeakMap` object.

#### Since
4.3.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a weak map, else `false`.

#### Example
```js
_.isWeakMap(new WeakMap);
// => true

_.isWeakMap(new Map);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_isweaksetvalue"><code>_.isWeakSet(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12254 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.isweakset "See the npm package") [&#x24C9;][1]

Checks if `value` is classified as a `WeakSet` object.

#### Since
4.3.0

#### Arguments
1. `value` *(&#42;)*: The value to check.

#### Returns
*(boolean)*: Returns `true` if `value` is a weak set, else `false`.

#### Example
```js
_.isWeakSet(new WeakSet);
// => true

_.isWeakSet(new Set);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ltvalue-other"><code>_.lt(value, other)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12281 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.lt "See the npm package") [&#x24C9;][1]

Checks if `value` is less than `other`.

#### Since
3.9.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.

#### Returns
*(boolean)*: Returns `true` if `value` is less than `other`, else `false`.

#### Example
```js
_.lt(1, 3);
// => true

_.lt(3, 3);
// => false

_.lt(3, 1);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ltevalue-other"><code>_.lte(value, other)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12306 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.lte "See the npm package") [&#x24C9;][1]

Checks if `value` is less than or equal to `other`.

#### Since
3.9.0

#### Arguments
1. `value` *(&#42;)*: The value to compare.
2. `other` *(&#42;)*: The other value to compare.

#### Returns
*(boolean)*: Returns `true` if `value` is less than or equal to `other`, else `false`.

#### Example
```js
_.lte(1, 3);
// => true

_.lte(3, 3);
// => true

_.lte(3, 1);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_toarrayvalue"><code>_.toArray(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12333 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.toarray "See the npm package") [&#x24C9;][1]

Converts `value` to an array.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(Array)*: Returns the converted array.

#### Example
```js
_.toArray({ 'a': 1, 'b': 2 });
// => [1, 2]

_.toArray('abc');
// => ['a', 'b', 'c']

_.toArray(1);
// => []

_.toArray(null);
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tofinitevalue"><code>_.toFinite(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12372 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tofinite "See the npm package") [&#x24C9;][1]

Converts `value` to a finite number.

#### Since
4.12.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(number)*: Returns the converted number.

#### Example
```js
_.toFinite(3.2);
// => 3.2

_.toFinite(Number.MIN_VALUE);
// => 5e-324

_.toFinite(Infinity);
// => 1.7976931348623157e+308

_.toFinite('3.2');
// => 3.2
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tointegervalue"><code>_.toInteger(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12410 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tointeger "See the npm package") [&#x24C9;][1]

Converts `value` to an integer.
<br>
<br>
**Note:** This method is loosely based on
[`ToInteger`](http://www.ecma-international.org/ecma-262/7.0/#sec-tointeger).

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(number)*: Returns the converted integer.

#### Example
```js
_.toInteger(3.2);
// => 3

_.toInteger(Number.MIN_VALUE);
// => 0

_.toInteger(Infinity);
// => 1.7976931348623157e+308

_.toInteger('3.2');
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tolengthvalue"><code>_.toLength(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12444 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tolength "See the npm package") [&#x24C9;][1]

Converts `value` to an integer suitable for use as the length of an
array-like object.
<br>
<br>
**Note:** This method is based on
[`ToLength`](http://ecma-international.org/ecma-262/7.0/#sec-tolength).

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(number)*: Returns the converted integer.

#### Example
```js
_.toLength(3.2);
// => 3

_.toLength(Number.MIN_VALUE);
// => 0

_.toLength(Infinity);
// => 4294967295

_.toLength('3.2');
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tonumbervalue"><code>_.toNumber(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12471 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tonumber "See the npm package") [&#x24C9;][1]

Converts `value` to a number.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to process.

#### Returns
*(number)*: Returns the number.

#### Example
```js
_.toNumber(3.2);
// => 3.2

_.toNumber(Number.MIN_VALUE);
// => 5e-324

_.toNumber(Infinity);
// => Infinity

_.toNumber('3.2');
// => 3.2
```
---

<!-- /div -->

<!-- div -->

<h3 id="_toplainobjectvalue"><code>_.toPlainObject(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12516 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.toplainobject "See the npm package") [&#x24C9;][1]

Converts `value` to a plain object flattening inherited enumerable string
keyed properties of `value` to own properties of the plain object.

#### Since
3.0.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(Object)*: Returns the converted plain object.

#### Example
```js
function Foo() {
  this.b = 2;
}

Foo.prototype.c = 3;

_.assign({ 'a': 1 }, new Foo);
// => { 'a': 1, 'b': 2 }

_.assign({ 'a': 1 }, _.toPlainObject(new Foo));
// => { 'a': 1, 'b': 2, 'c': 3 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tosafeintegervalue"><code>_.toSafeInteger(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12544 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tosafeinteger "See the npm package") [&#x24C9;][1]

Converts `value` to a safe integer. A safe integer can be compared and
represented correctly.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(number)*: Returns the converted integer.

#### Example
```js
_.toSafeInteger(3.2);
// => 3

_.toSafeInteger(Number.MIN_VALUE);
// => 0

_.toSafeInteger(Infinity);
// => 9007199254740991

_.toSafeInteger('3.2');
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tostringvalue"><code>_.toString(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L12571 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tostring "See the npm package") [&#x24C9;][1]

Converts `value` to a string. An empty string is returned for `null`
and `undefined` values. The sign of `-0` is preserved.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(string)*: Returns the converted string.

#### Example
```js
_.toString(null);
// => ''

_.toString(-0);
// => '-0'

_.toString([1, 2, 3]);
// => '1,2,3'
```
---