* <a href="#_attemptfunc-args">`_.attempt`</a>
* <a href="#_bindallobject-methodnames">`_.bindAll`</a>
* <a href="#_condpairs">`_.cond`</a>
* <a href="#_conformssource">`_.conforms`</a>
* <a href="#_constantvalue">`_.constant`</a>
* <a href="#_defaulttovalue-defaultvalue">`_.defaultTo`</a>
* <a href="#_flowfuncs">`_.flow`</a>
* <a href="#_flowrightfuncs">`_.flowRight`</a>
* <a href="#_identityvalue">`_.identity`</a>
* <a href="#_iterateefunc_identity">`_.iteratee`</a>
* <a href="#_matchessource">`_.matches`</a>
* <a href="#_matchespropertypath-srcvalue">`_.matchesProperty`</a>
* <a href="#_methodpath-args">`_.method`</a>
* <a href="#_methodofobject-args">`_.methodOf`</a>
* <a href="#_mixinobjectlodash-source-options">`_.mixin`</a>
* <a href="#_noconflict">`_.noConflict`</a>
* <a href="#_noop">`_.noop`</a>
* <a href="#_nthargn0">`_.nthArg`</a>
* <a href="#_overiteratees_identity">`_.over`</a>
* <a href="#_overeverypredicates_identity">`_.overEvery`</a>
* <a href="#_oversomepredicates_identity">`_.overSome`</a>
* <a href="#_propertypath">`_.property`</a>
* <a href="#_propertyofobject">`_.propertyOf`</a>
* <a href="#_rangestart0-end-step1">`_.range`</a>
* <a href="#_rangerightstart0-end-step1">`_.rangeRight`</a>
* <a href="#_runincontextcontextroot">`_.runInContext`</a>
* <a href="#_stubarray">`_.stubArray`</a>
* <a href="#_stubfalse">`_.stubFalse`</a>
* <a href="#_stubobject">`_.stubObject`</a>
* <a href="#_stubstring">`_.stubString`</a>
* <a href="#_stubtrue">`_.stubTrue`</a>
* <a href="#_timesn-iteratee_identity">`_.times`</a>
* <a href="#_topathvalue">`_.toPath`</a>
* <a href="#_uniqueidprefix">`_.uniqueId`</a>


## `“Util” Methods`

<!-- div -->

<h3 id="_attemptfunc-args"><code>_.attempt(func, [args])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15225 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.attempt "See the npm package") [&#x24C9;][1]

Attempts to invoke `func`, returning either the result or the caught error
object. Any additional arguments are provided to `func` when it's invoked.

#### Since
3.0.0

#### Arguments
1. `func` *(Function)*: The function to attempt.
2. `[args]` *(...&#42;)*: The arguments to invoke `func` with.

#### Returns
*(&#42;)*: Returns the `func` result or error object.

#### Example
```js
// Avoid throwing errors for invalid selectors.
var elements = _.attempt(function(selector) {
  return document.querySelectorAll(selector);
}, '>_>');

if (_.isError(elements)) {
  elements = [];
}
```
---

<!-- /div -->

<!-- div -->

<h3 id="_bindallobject-methodnames"><code>_.bindAll(object, methodNames)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15259 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.bindall "See the npm package") [&#x24C9;][1]

Binds methods of an object to the object itself, overwriting the existing
method.
<br>
<br>
**Note:** This method doesn't set the "length" property of bound functions.

#### Since
0.1.0

#### Arguments
1. `object` *(Object)*: The object to bind and assign the bound methods to.
2. `methodNames` *(...(string|string&#91;&#93;))*: The object method names to bind.

#### Returns
*(Object)*: Returns `object`.

#### Example
```js
var view = {
  'label': 'docs',
  'click': function() {
    console.log('clicked ' + this.label);
  }
};

_.bindAll(view, ['click']);
jQuery(element).on('click', view.click);
// => Logs 'clicked docs' when clicked.
```
---

<!-- /div -->

<!-- div -->

<h3 id="_condpairs"><code>_.cond(pairs)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15296 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.cond "See the npm package") [&#x24C9;][1]

Creates a function that iterates over `pairs` and invokes the corresponding
function of the first predicate to return truthy. The predicate-function
pairs are invoked with the `this` binding and arguments of the created
function.

#### Since
4.0.0

#### Arguments
1. `pairs` *(Array)*: The predicate-function pairs.

#### Returns
*(Function)*: Returns the new composite function.

#### Example
```js
var func = _.cond([
  [_.matches({ 'a': 1 }),           _.constant('matches A')],
  [_.conforms({ 'b': _.isNumber }), _.constant('matches B')],
  [_.stubTrue,                      _.constant('no match')]
]);

func({ 'a': 1, 'b': 2 });
// => 'matches A'

func({ 'a': 0, 'b': 1 });
// => 'matches B'

func({ 'a': '1', 'b': '2' });
// => 'no match'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_conformssource"><code>_.conforms(source)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15342 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.conforms "See the npm package") [&#x24C9;][1]

Creates a function that invokes the predicate properties of `source` with
the corresponding property values of a given object, returning `true` if
all predicates return truthy, else `false`.
<br>
<br>
**Note:** The created function is equivalent to `_.conformsTo` with
`source` partially applied.

#### Since
4.0.0

#### Arguments
1. `source` *(Object)*: The object of property predicates to conform to.

#### Returns
*(Function)*: Returns the new spec function.

#### Example
```js
var objects = [
  { 'a': 2, 'b': 1 },
  { 'a': 1, 'b': 2 }
];

_.filter(objects, _.conforms({ 'b': function(n) { return n > 1; } }));
// => [{ 'a': 1, 'b': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_constantvalue"><code>_.constant(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15365 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.constant "See the npm package") [&#x24C9;][1]

Creates a function that returns `value`.

#### Since
2.4.0

#### Arguments
1. `value` *(&#42;)*: The value to return from the new function.

#### Returns
*(Function)*: Returns the new constant function.

#### Example
```js
var objects = _.times(2, _.constant({ 'a': 1 }));

console.log(objects);
// => [{ 'a': 1 }, { 'a': 1 }]

console.log(objects[0] === objects[1]);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_defaulttovalue-defaultvalue"><code>_.defaultTo(value, defaultValue)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15391 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.defaultto "See the npm package") [&#x24C9;][1]

Checks `value` to determine whether a default value should be returned in
its place. The `defaultValue` is returned if `value` is `NaN`, `null`,
or `undefined`.

#### Since
4.14.0

#### Arguments
1. `value` *(&#42;)*: The value to check.
2. `defaultValue` *(&#42;)*: The default value.

#### Returns
*(&#42;)*: Returns the resolved value.

#### Example
```js
_.defaultTo(1, 10);
// => 1

_.defaultTo(undefined, 10);
// => 10
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flowfuncs"><code>_.flow([funcs])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15417 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flow "See the npm package") [&#x24C9;][1]

Creates a function that returns the result of invoking the given functions
with the `this` binding of the created function, where each successive
invocation is supplied the return value of the previous.

#### Since
3.0.0

#### Arguments
1. `[funcs]` *(...(Function|Function&#91;&#93;))*: The functions to invoke.

#### Returns
*(Function)*: Returns the new composite function.

#### Example
```js
function square(n) {
  return n * n;
}

var addSquare = _.flow([_.add, square]);
addSquare(1, 2);
// => 9
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flowrightfuncs"><code>_.flowRight([funcs])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15440 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flowright "See the npm package") [&#x24C9;][1]

This method is like `_.flow` except that it creates a function that
invokes the given functions from right to left.

#### Since
3.0.0

#### Arguments
1. `[funcs]` *(...(Function|Function&#91;&#93;))*: The functions to invoke.

#### Returns
*(Function)*: Returns the new composite function.

#### Example
```js
function square(n) {
  return n * n;
}

var addSquare = _.flowRight([square, _.add]);
addSquare(1, 2);
// => 9
```
---

<!-- /div -->

<!-- div -->

<h3 id="_identityvalue"><code>_.identity(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15458 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.identity "See the npm package") [&#x24C9;][1]

This method returns the first argument it receives.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: Any value.

#### Returns
*(&#42;)*: Returns `value`.

#### Example
```js
var object = { 'a': 1 };

console.log(_.identity(object) === object);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_iterateefunc_identity"><code>_.iteratee([func=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15504 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.iteratee "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with the arguments of the created
function. If `func` is a property name, the created function returns the
property value for a given element. If `func` is an array or object, the
created function returns `true` for elements that contain the equivalent
source properties, otherwise it returns `false`.

#### Since
4.0.0

#### Arguments
1. `[func=_.identity]` *(&#42;)*: The value to convert to a callback.

#### Returns
*(Function)*: Returns the callback.

#### Example
```js
var users = [
  { 'user': 'barney', 'age': 36, 'active': true },
  { 'user': 'fred',   'age': 40, 'active': false }
];

// The `_.matches` iteratee shorthand.
_.filter(users, _.iteratee({ 'user': 'barney', 'active': true }));
// => [{ 'user': 'barney', 'age': 36, 'active': true }]

// The `_.matchesProperty` iteratee shorthand.
_.filter(users, _.iteratee(['user', 'fred']));
// => [{ 'user': 'fred', 'age': 40 }]

// The `_.property` iteratee shorthand.
_.map(users, _.iteratee('user'));
// => ['barney', 'fred']

// Create custom iteratee shorthands.
_.iteratee = _.wrap(_.iteratee, function(iteratee, func) {
  return !_.isRegExp(func) ? iteratee(func) : function(string) {
    return func.test(string);
  };
});

_.filter(['abc', 'def'], /ef/);
// => ['def']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_matchessource"><code>_.matches(source)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15536 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.matches "See the npm package") [&#x24C9;][1]

Creates a function that performs a partial deep comparison between a given
object and `source`, returning `true` if the given object has equivalent
property values, else `false`.
<br>
<br>
**Note:** The created function is equivalent to `_.isMatch` with `source`
partially applied.
<br>
<br>
Partial comparisons will match empty array and empty object `source`
values against any array or object value, respectively. See `_.isEqual`
for a list of supported value comparisons.

#### Since
3.0.0

#### Arguments
1. `source` *(Object)*: The object of property values to match.

#### Returns
*(Function)*: Returns the new spec function.

#### Example
```js
var objects = [
  { 'a': 1, 'b': 2, 'c': 3 },
  { 'a': 4, 'b': 5, 'c': 6 }
];

_.filter(objects, _.matches({ 'a': 4, 'c': 6 }));
// => [{ 'a': 4, 'b': 5, 'c': 6 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_matchespropertypath-srcvalue"><code>_.matchesProperty(path, srcValue)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15566 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.matchesproperty "See the npm package") [&#x24C9;][1]

Creates a function that performs a partial deep comparison between the
value at `path` of a given object to `srcValue`, returning `true` if the
object value is equivalent, else `false`.
<br>
<br>
**Note:** Partial comparisons will match empty array and empty object
`srcValue` values against any array or object value, respectively. See
`_.isEqual` for a list of supported value comparisons.

#### Since
3.2.0

#### Arguments
1. `path` *(Array|string)*: The path of the property to get.
2. `srcValue` *(&#42;)*: The value to match.

#### Returns
*(Function)*: Returns the new spec function.

#### Example
```js
var objects = [
  { 'a': 1, 'b': 2, 'c': 3 },
  { 'a': 4, 'b': 5, 'c': 6 }
];

_.find(objects, _.matchesProperty('a', 4));
// => { 'a': 4, 'b': 5, 'c': 6 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_methodpath-args"><code>_.method(path, [args])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15594 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.method "See the npm package") [&#x24C9;][1]

Creates a function that invokes the method at `path` of a given object.
Any additional arguments are provided to the invoked method.

#### Since
3.7.0

#### Arguments
1. `path` *(Array|string)*: The path of the method to invoke.
2. `[args]` *(...&#42;)*: The arguments to invoke the method with.

#### Returns
*(Function)*: Returns the new invoker function.

#### Example
```js
var objects = [
  { 'a': { 'b': _.constant(2) } },
  { 'a': { 'b': _.constant(1) } }
];

_.map(objects, _.method('a.b'));
// => [2, 1]

_.map(objects, _.method(['a', 'b']));
// => [2, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_methodofobject-args"><code>_.methodOf(object, [args])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15623 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.methodof "See the npm package") [&#x24C9;][1]

The opposite of `_.method`; this method creates a function that invokes
the method at a given path of `object`. Any additional arguments are
provided to the invoked method.

#### Since
3.7.0

#### Arguments
1. `object` *(Object)*: The object to query.
2. `[args]` *(...&#42;)*: The arguments to invoke the method with.

#### Returns
*(Function)*: Returns the new invoker function.

#### Example
```js
var array = _.times(3, _.constant),
    object = { 'a': array, 'b': array, 'c': array };

_.map(['a[2]', 'c[0]'], _.methodOf(object));
// => [2, 0]

_.map([['a', '2'], ['c', '0']], _.methodOf(object));
// => [2, 0]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_mixinobjectlodash-source-options"><code>_.mixin([object=lodash], source, [options={}])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15665 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.mixin "See the npm package") [&#x24C9;][1]

Adds all own enumerable string keyed function properties of a source
object to the destination object. If `object` is a function, then methods
are added to its prototype as well.
<br>
<br>
**Note:** Use `_.runInContext` to create a pristine `lodash` function to
avoid conflicts caused by modifying the original.

#### Since
0.1.0

#### Arguments
1. `[object=lodash]` *(Function|Object)*: The destination object.
2. `source` *(Object)*: The object of functions to add.
3. `[options={}]` *(Object)*: The options object.
4. `[options.chain=true]` *(boolean)*: Specify whether mixins are chainable.

#### Returns
*(&#42;)*: Returns `object`.

#### Example
```js
function vowels(string) {
  return _.filter(string, function(v) {
    return /[aeiou]/i.test(v);
  });
}

_.mixin({ 'vowels': vowels });
_.vowels('fred');
// => ['e']

_('fred').vowels().value();
// => ['e']

_.mixin({ 'vowels': vowels }, { 'chain': false });
_('fred').vowels();
// => ['e']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_noconflict"><code>_.noConflict()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15714 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.noconflict "See the npm package") [&#x24C9;][1]

Reverts the `_` variable to its previous value and returns a reference to
the `lodash` function.

#### Since
0.1.0

#### Returns
*(Function)*: Returns the `lodash` function.

#### Example
```js
var lodash = _.noConflict();
```
---

<!-- /div -->

<!-- div -->

<h3 id="_noop"><code>_.noop()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15733 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.noop "See the npm package") [&#x24C9;][1]

This method returns `undefined`.

#### Since
2.3.0

#### Example
```js
_.times(2, _.noop);
// => [undefined, undefined]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_nthargn0"><code>_.nthArg([n=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15757 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.ntharg "See the npm package") [&#x24C9;][1]

Creates a function that gets the argument at index `n`. If `n` is negative,
the nth argument from the end is returned.

#### Since
4.0.0

#### Arguments
1. `[n=0]` *(number)*: The index of the argument to return.

#### Returns
*(Function)*: Returns the new pass-thru function.

#### Example
```js
var func = _.nthArg(1);
func('a', 'b', 'c', 'd');
// => 'b'

var func = _.nthArg(-2);
func('a', 'b', 'c', 'd');
// => 'c'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_overiteratees_identity"><code>_.over([iteratees=[_.identity]])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15782 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.over "See the npm package") [&#x24C9;][1]

Creates a function that invokes `iteratees` with the arguments it receives
and returns their results.

#### Since
4.0.0

#### Arguments
1. `[iteratees=[_.identity]]` *(...(Function|Function&#91;&#93;))*: The iteratees to invoke.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var func = _.over([Math.max, Math.min]);

func(1, 2, 3, 4);
// => [4, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_overeverypredicates_identity"><code>_.overEvery([predicates=[_.identity]])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15808 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.overevery "See the npm package") [&#x24C9;][1]

Creates a function that checks if **all** of the `predicates` return
truthy when invoked with the arguments it receives.

#### Since
4.0.0

#### Arguments
1. `[predicates=[_.identity]]` *(...(Function|Function&#91;&#93;))*: The predicates to check.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var func = _.overEvery([Boolean, isFinite]);

func('1');
// => true

func(null);
// => false

func(NaN);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_oversomepredicates_identity"><code>_.overSome([predicates=[_.identity]])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15834 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.oversome "See the npm package") [&#x24C9;][1]

Creates a function that checks if **any** of the `predicates` return
truthy when invoked with the arguments it receives.

#### Since
4.0.0

#### Arguments
1. `[predicates=[_.identity]]` *(...(Function|Function&#91;&#93;))*: The predicates to check.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var func = _.overSome([Boolean, isFinite]);

func('1');
// => true

func(null);
// => true

func(NaN);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_propertypath"><code>_.property(path)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15858 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.property "See the npm package") [&#x24C9;][1]

Creates a function that returns the value at `path` of a given object.

#### Since
2.4.0

#### Arguments
1. `path` *(Array|string)*: The path of the property to get.

#### Returns
*(Function)*: Returns the new accessor function.

#### Example
```js
var objects = [
  { 'a': { 'b': 2 } },
  { 'a': { 'b': 1 } }
];

_.map(objects, _.property('a.b'));
// => [2, 1]

_.map(_.sortBy(objects, _.property(['a', 'b'])), 'a.b');
// => [1, 2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_propertyofobject"><code>_.propertyOf(object)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15883 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.propertyof "See the npm package") [&#x24C9;][1]

The opposite of `_.property`; this method creates a function that returns
the value at a given path of `object`.

#### Since
3.0.0

#### Arguments
1. `object` *(Object)*: The object to query.

#### Returns
*(Function)*: Returns the new accessor function.

#### Example
```js
var array = [0, 1, 2],
    object = { 'a': array, 'b': array, 'c': array };

_.map(['a[2]', 'c[0]'], _.propertyOf(object));
// => [2, 0]

_.map([['a', '2'], ['c', '0']], _.propertyOf(object));
// => [2, 0]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_rangestart0-end-step1"><code>_.range([start=0], end, [step=1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15930 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.range "See the npm package") [&#x24C9;][1]

Creates an array of numbers *(positive and/or negative)* progressing from
`start` up to, but not including, `end`. A step of `-1` is used if a negative
`start` is specified without an `end` or `step`. If `end` is not specified,
it's set to `start` with `start` then set to `0`.
<br>
<br>
**Note:** JavaScript follows the IEEE-754 standard for resolving
floating-point values which can produce unexpected results.

#### Since
0.1.0

#### Arguments
1. `[start=0]` *(number)*: The start of the range.
2. `end` *(number)*: The end of the range.
3. `[step=1]` *(number)*: The value to increment or decrement by.

#### Returns
*(Array)*: Returns the range of numbers.

#### Example
```js
_.range(4);
// => [0, 1, 2, 3]

_.range(-4);
// => [0, -1, -2, -3]

_.range(1, 5);
// => [1, 2, 3, 4]

_.range(0, 20, 5);
// => [0, 5, 10, 15]

_.range(0, -4, -1);
// => [0, -1, -2, -3]

_.range(1, 4, 0);
// => [1, 1, 1]

_.range(0);
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_rangerightstart0-end-step1"><code>_.rangeRight([start=0], end, [step=1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15968 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.rangeright "See the npm package") [&#x24C9;][1]

This method is like `_.range` except that it populates values in
descending order.

#### Since
4.0.0

#### Arguments
1. `[start=0]` *(number)*: The start of the range.
2. `end` *(number)*: The end of the range.
3. `[step=1]` *(number)*: The value to increment or decrement by.

#### Returns
*(Array)*: Returns the range of numbers.

#### Example
```js
_.rangeRight(4);
// => [3, 2, 1, 0]

_.rangeRight(-4);
// => [-3, -2, -1, 0]

_.rangeRight(1, 5);
// => [4, 3, 2, 1]

_.rangeRight(0, 20, 5);
// => [15, 10, 5, 0]

_.rangeRight(0, -4, -1);
// => [-3, -2, -1, 0]

_.rangeRight(1, 4, 0);
// => [1, 1, 1]

_.rangeRight(0);
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_runincontextcontextroot"><code>_.runInContext([context=root])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L1427 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.runincontext "See the npm package") [&#x24C9;][1]

Create a new pristine `lodash` function using the `context` object.

#### Since
1.1.0

#### Arguments
1. `[context=root]` *(Object)*: The context object.

#### Returns
*(Function)*: Returns a new `lodash` function.

#### Example
```js
_.mixin({ 'foo': _.constant('foo') });

var lodash = _.runInContext();
lodash.mixin({ 'bar': lodash.constant('bar') });

_.isFunction(_.foo);
// => true
_.isFunction(_.bar);
// => false

lodash.isFunction(lodash.foo);
// => false
lodash.isFunction(lodash.bar);
// => true

// Create a suped-up `defer` in Node.js.
var defer = _.runInContext({ 'setTimeout': setImmediate }).defer;
```
---

<!-- /div -->

<!-- div -->

<h3 id="_stubarray"><code>_.stubArray()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15988 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.stubarray "See the npm package") [&#x24C9;][1]

This method returns a new empty array.

#### Since
4.13.0

#### Returns
*(Array)*: Returns the new empty array.

#### Example
```js
var arrays = _.times(2, _.stubArray);

console.log(arrays);
// => [[], []]

console.log(arrays[0] === arrays[1]);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_stubfalse"><code>_.stubFalse()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16005 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.stubfalse "See the npm package") [&#x24C9;][1]

This method returns `false`.

#### Since
4.13.0

#### Returns
*(boolean)*: Returns `false`.

#### Example
```js
_.times(2, _.stubFalse);
// => [false, false]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_stubobject"><code>_.stubObject()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16027 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.stubobject "See the npm package") [&#x24C9;][1]

This method returns a new empty object.

#### Since
4.13.0

#### Returns
*(Object)*: Returns the new empty object.

#### Example
```js
var objects = _.times(2, _.stubObject);

console.log(objects);
// => [{}, {}]

console.log(objects[0] === objects[1]);
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_stubstring"><code>_.stubString()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16044 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.stubstring "See the npm package") [&#x24C9;][1]

This method returns an empty string.

#### Since
4.13.0

#### Returns
*(string)*: Returns the empty string.

#### Example
```js
_.times(2, _.stubString);
// => ['', '']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_stubtrue"><code>_.stubTrue()</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16061 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.stubtrue "See the npm package") [&#x24C9;][1]

This method returns `true`.

#### Since
4.13.0

#### Returns
*(boolean)*: Returns `true`.

#### Example
```js
_.times(2, _.stubTrue);
// => [true, true]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_timesn-iteratee_identity"><code>_.times(n, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16084 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.times "See the npm package") [&#x24C9;][1]

Invokes the iteratee `n` times, returning an array of the results of
each invocation. The iteratee is invoked with one argument; *(index)*.

#### Since
0.1.0

#### Arguments
1. `n` *(number)*: The number of times to invoke `iteratee`.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the array of results.

#### Example
```js
_.times(3, String);
// => ['0', '1', '2']

 _.times(4, _.constant(0));
// => [0, 0, 0, 0]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_topathvalue"><code>_.toPath(value)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16119 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.topath "See the npm package") [&#x24C9;][1]

Converts `value` to a property path array.

#### Since
4.0.0

#### Arguments
1. `value` *(&#42;)*: The value to convert.

#### Returns
*(Array)*: Returns the new property path array.

#### Example
```js
_.toPath('a.b.c');
// => ['a', 'b', 'c']

_.toPath('a[0].b.c');
// => ['a', '0', 'b', 'c']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_uniqueidprefix"><code>_.uniqueId([prefix=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L16143 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.uniqueid "See the npm package") [&#x24C9;][1]

Generates a unique ID. If `prefix` is given, the ID is appended to it.

#### Since
0.1.0

#### Arguments
1. `[prefix='']` *(string)*: The value to prefix the ID with.

#### Returns
*(string)*: Returns the unique ID.

#### Example
```js
_.uniqueId('contact_');
// => 'contact_104'

_.uniqueId();
// => '105'
```
---

<!-- /div -->

<!-- /div -->

<!-- div -->

