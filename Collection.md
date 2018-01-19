* <a href="#_countbycollection-iteratee_identity">`_.countBy`</a>
* <a href="#_foreachcollection-iteratee_identity" class="alias">`_.each` -> `forEach`</a>
* <a href="#_foreachrightcollection-iteratee_identity" class="alias">`_.eachRight` -> `forEachRight`</a>
* <a href="#_everycollection-predicate_identity">`_.every`</a>
* <a href="#_filtercollection-predicate_identity">`_.filter`</a>
* <a href="#_findcollection-predicate_identity-fromindex0">`_.find`</a>
* <a href="#_findlastcollection-predicate_identity-fromindexcollectionlength-1">`_.findLast`</a>
* <a href="#_flatmapcollection-iteratee_identity">`_.flatMap`</a>
* <a href="#_flatmapdeepcollection-iteratee_identity">`_.flatMapDeep`</a>
* <a href="#_flatmapdepthcollection-iteratee_identity-depth1">`_.flatMapDepth`</a>
* <a href="#_foreachcollection-iteratee_identity">`_.forEach`</a>
* <a href="#_foreachrightcollection-iteratee_identity">`_.forEachRight`</a>
* <a href="#_groupbycollection-iteratee_identity">`_.groupBy`</a>
* <a href="#_includescollection-value-fromindex0">`_.includes`</a>
* <a href="#_invokemapcollection-path-args">`_.invokeMap`</a>
* <a href="#_keybycollection-iteratee_identity">`_.keyBy`</a>
* <a href="#_mapcollection-iteratee_identity">`_.map`</a>
* <a href="#_orderbycollection-iteratees_identity-orders">`_.orderBy`</a>
* <a href="#_partitioncollection-predicate_identity">`_.partition`</a>
* <a href="#_reducecollection-iteratee_identity-accumulator">`_.reduce`</a>
* <a href="#_reducerightcollection-iteratee_identity-accumulator">`_.reduceRight`</a>
* <a href="#_rejectcollection-predicate_identity">`_.reject`</a>
* <a href="#_samplecollection">`_.sample`</a>
* <a href="#_samplesizecollection-n1">`_.sampleSize`</a>
* <a href="#_shufflecollection">`_.shuffle`</a>
* <a href="#_sizecollection">`_.size`</a>
* <a href="#_somecollection-predicate_identity">`_.some`</a>
* <a href="#_sortbycollection-iteratees_identity">`_.sortBy`</a>


## `“Collection” Methods`

<!-- div -->

<h3 id="_countbycollection-iteratee_identity"><code>_.countBy(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9094 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.countby "See the npm package") [&#x24C9;][1]

Creates an object composed of keys generated from the results of running
each element of `collection` thru `iteratee`. The corresponding value of
each key is the number of times the key was returned by `iteratee`. The
iteratee is invoked with one argument: *(value)*.

#### Since
0.5.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee to transform keys.

#### Returns
*(Object)*: Returns the composed aggregate object.

#### Example
```js
_.countBy([6.1, 4.2, 6.3], Math.floor);
// => { '4': 1, '6': 2 }

// The `_.property` iteratee shorthand.
_.countBy(['one', 'two', 'three'], 'length');
// => { '3': 2, '5': 1 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_everycollection-predicate_identity"><code>_.every(collection, [predicate=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9143 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.every "See the npm package") [&#x24C9;][1]

Checks if `predicate` returns truthy for **all** elements of `collection`.
Iteration is stopped once `predicate` returns falsey. The predicate is
invoked with three arguments: *(value, index|key, collection)*.
<br>
<br>
**Note:** This method returns `true` for
[empty collections](https://en.wikipedia.org/wiki/Empty_set) because
[everything is true](https://en.wikipedia.org/wiki/Vacuous_truth) of
elements of empty collections.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(boolean)*: Returns `true` if all elements pass the predicate check, else `false`.

#### Example
```js
_.every([true, 1, null, 'yes'], Boolean);
// => false

var users = [
  { 'user': 'barney', 'age': 36, 'active': false },
  { 'user': 'fred',   'age': 40, 'active': false }
];

// The `_.matches` iteratee shorthand.
_.every(users, { 'user': 'barney', 'active': false });
// => false

// The `_.matchesProperty` iteratee shorthand.
_.every(users, ['active', false]);
// => true

// The `_.property` iteratee shorthand.
_.every(users, 'active');
// => false
```
---

<!-- /div -->

<!-- div -->

<h3 id="_filtercollection-predicate_identity"><code>_.filter(collection, [predicate=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9188 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.filter "See the npm package") [&#x24C9;][1]

Iterates over elements of `collection`, returning an array of all elements
`predicate` returns truthy for. The predicate is invoked with three
arguments: *(value, index|key, collection)*.
<br>
<br>
**Note:** Unlike `_.remove`, this method returns a new array.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the new filtered array.

#### Example
```js
var users = [
  { 'user': 'barney', 'age': 36, 'active': true },
  { 'user': 'fred',   'age': 40, 'active': false }
];

_.filter(users, function(o) { return !o.active; });
// => objects for ['fred']

// The `_.matches` iteratee shorthand.
_.filter(users, { 'age': 36, 'active': true });
// => objects for ['barney']

// The `_.matchesProperty` iteratee shorthand.
_.filter(users, ['active', false]);
// => objects for ['fred']

// The `_.property` iteratee shorthand.
_.filter(users, 'active');
// => objects for ['barney']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_findcollection-predicate_identity-fromindex0"><code>_.find(collection, [predicate=_.identity], [fromIndex=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9229 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.find "See the npm package") [&#x24C9;][1]

Iterates over elements of `collection`, returning the first element
`predicate` returns truthy for. The predicate is invoked with three
arguments: *(value, index|key, collection)*.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to inspect.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.
3. `[fromIndex=0]` *(number)*: The index to search from.

#### Returns
*(&#42;)*: Returns the matched element, else `undefined`.

#### Example
```js
var users = [
  { 'user': 'barney',  'age': 36, 'active': true },
  { 'user': 'fred',    'age': 40, 'active': false },
  { 'user': 'pebbles', 'age': 1,  'active': true }
];

_.find(users, function(o) { return o.age < 40; });
// => object for 'barney'

// The `_.matches` iteratee shorthand.
_.find(users, { 'age': 1, 'active': true });
// => object for 'pebbles'

// The `_.matchesProperty` iteratee shorthand.
_.find(users, ['active', false]);
// => object for 'fred'

// The `_.property` iteratee shorthand.
_.find(users, 'active');
// => object for 'barney'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_findlastcollection-predicate_identity-fromindexcollectionlength-1"><code>_.findLast(collection, [predicate=_.identity], [fromIndex=collection.length-1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9250 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.findlast "See the npm package") [&#x24C9;][1]

This method is like `_.find` except that it iterates over elements of
`collection` from right to left.

#### Since
2.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to inspect.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.
3. `[fromIndex=collection.length-1]` *(number)*: The index to search from.

#### Returns
*(&#42;)*: Returns the matched element, else `undefined`.

#### Example
```js
_.findLast([1, 2, 3, 4], function(n) {
  return n % 2 == 1;
});
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flatmapcollection-iteratee_identity"><code>_.flatMap(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9273 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flatmap "See the npm package") [&#x24C9;][1]

Creates a flattened array of values by running each element in `collection`
thru `iteratee` and flattening the mapped results. The iteratee is invoked
with three arguments: *(value, index|key, collection)*.

#### Since
4.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the new flattened array.

#### Example
```js
function duplicate(n) {
  return [n, n];
}

_.flatMap([1, 2], duplicate);
// => [1, 1, 2, 2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flatmapdeepcollection-iteratee_identity"><code>_.flatMapDeep(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9297 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flatmapdeep "See the npm package") [&#x24C9;][1]

This method is like `_.flatMap` except that it recursively flattens the
mapped results.

#### Since
4.7.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the new flattened array.

#### Example
```js
function duplicate(n) {
  return [[[n, n]]];
}

_.flatMapDeep([1, 2], duplicate);
// => [1, 1, 2, 2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flatmapdepthcollection-iteratee_identity-depth1"><code>_.flatMapDepth(collection, [iteratee=_.identity], [depth=1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9322 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flatmapdepth "See the npm package") [&#x24C9;][1]

This method is like `_.flatMap` except that it recursively flattens the
mapped results up to `depth` times.

#### Since
4.7.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.
3. `[depth=1]` *(number)*: The maximum recursion depth.

#### Returns
*(Array)*: Returns the new flattened array.

#### Example
```js
function duplicate(n) {
  return [[[n, n]]];
}

_.flatMapDepth([1, 2], duplicate, 2);
// => [[1, 1], [2, 2]]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_foreachcollection-iteratee_identity"><code>_.forEach(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9357 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.foreach "See the npm package") [&#x24C9;][1]

Iterates over elements of `collection` and invokes `iteratee` for each element.
The iteratee is invoked with three arguments: *(value, index|key, collection)*.
Iteratee functions may exit iteration early by explicitly returning `false`.
<br>
<br>
**Note:** As with other "Collections" methods, objects with a "length"
property are iterated like arrays. To avoid this behavior use `_.forIn`
or `_.forOwn` for object iteration.

#### Since
0.1.0

#### Aliases
*_.each*

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(&#42;)*: Returns `collection`.

#### Example
```js
_.forEach([1, 2], function(value) {
  console.log(value);
});
// => Logs `1` then `2`.

_.forEach({ 'a': 1, 'b': 2 }, function(value, key) {
  console.log(key);
});
// => Logs 'a' then 'b' (iteration order is not guaranteed).
```
---

<!-- /div -->

<!-- div -->

<h3 id="_foreachrightcollection-iteratee_identity"><code>_.forEachRight(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9382 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.foreachright "See the npm package") [&#x24C9;][1]

This method is like `_.forEach` except that it iterates over elements of
`collection` from right to left.

#### Since
2.0.0

#### Aliases
*_.eachRight*

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(&#42;)*: Returns `collection`.

#### Example
```js
_.forEachRight([1, 2], function(value) {
  console.log(value);
});
// => Logs `2` then `1`.
```
---

<!-- /div -->

<!-- div -->

<h3 id="_groupbycollection-iteratee_identity"><code>_.groupBy(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9410 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.groupby "See the npm package") [&#x24C9;][1]

Creates an object composed of keys generated from the results of running
each element of `collection` thru `iteratee`. The order of grouped values
is determined by the order they occur in `collection`. The corresponding
value of each key is an array of elements responsible for generating the
key. The iteratee is invoked with one argument: *(value)*.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee to transform keys.

#### Returns
*(Object)*: Returns the composed aggregate object.

#### Example
```js
_.groupBy([6.1, 4.2, 6.3], Math.floor);
// => { '4': [4.2], '6': [6.1, 6.3] }

// The `_.property` iteratee shorthand.
_.groupBy(['one', 'two', 'three'], 'length');
// => { '3': ['one', 'two'], '5': ['three'] }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_includescollection-value-fromindex0"><code>_.includes(collection, value, [fromIndex=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9448 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.includes "See the npm package") [&#x24C9;][1]

Checks if `value` is in `collection`. If `collection` is a string, it's
checked for a substring of `value`, otherwise
[`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
is used for equality comparisons. If `fromIndex` is negative, it's used as
the offset from the end of `collection`.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object|string)*: The collection to inspect.
2. `value` *(&#42;)*: The value to search for.
3. `[fromIndex=0]` *(number)*: The index to search from.

#### Returns
*(boolean)*: Returns `true` if `value` is found, else `false`.

#### Example
```js
_.includes([1, 2, 3], 1);
// => true

_.includes([1, 2, 3], 1, 2);
// => false

_.includes({ 'a': 1, 'b': 2 }, 1);
// => true

_.includes('abcd', 'bc');
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_invokemapcollection-path-args"><code>_.invokeMap(collection, path, [args])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9484 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.invokemap "See the npm package") [&#x24C9;][1]

Invokes the method at `path` of each element in `collection`, returning
an array of the results of each invoked method. Any additional arguments
are provided to each invoked method. If `path` is a function, it's invoked
for, and `this` bound to, each element in `collection`.

#### Since
4.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `path` *(Array|Function|string)*: The path of the method to invoke or the function invoked per iteration.
3. `[args]` *(...&#42;)*: The arguments to invoke each method with.

#### Returns
*(Array)*: Returns the array of results.

#### Example
```js
_.invokeMap([[5, 1, 7], [3, 2, 1]], 'sort');
// => [[1, 5, 7], [1, 2, 3]]

_.invokeMap([123, 456], String.prototype.split, '');
// => [['1', '2', '3'], ['4', '5', '6']]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_keybycollection-iteratee_identity"><code>_.keyBy(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9523 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.keyby "See the npm package") [&#x24C9;][1]

Creates an object composed of keys generated from the results of running
each element of `collection` thru `iteratee`. The corresponding value of
each key is the last element responsible for generating the key. The
iteratee is invoked with one argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The iteratee to transform keys.

#### Returns
*(Object)*: Returns the composed aggregate object.

#### Example
```js
var array = [
  { 'dir': 'left', 'code': 97 },
  { 'dir': 'right', 'code': 100 }
];

_.keyBy(array, function(o) {
  return String.fromCharCode(o.code);
});
// => { 'a': { 'dir': 'left', 'code': 97 }, 'd': { 'dir': 'right', 'code': 100 } }

_.keyBy(array, 'dir');
// => { 'left': { 'dir': 'left', 'code': 97 }, 'right': { 'dir': 'right', 'code': 100 } }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_mapcollection-iteratee_identity"><code>_.map(collection, [iteratee=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9569 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.map "See the npm package") [&#x24C9;][1]

Creates an array of values by running each element in `collection` thru
`iteratee`. The iteratee is invoked with three arguments:<br>
*(value, index|key, collection)*.
<br>
<br>
Many lodash methods are guarded to work as iteratees for methods like
`_.every`, `_.filter`, `_.map`, `_.mapValues`, `_.reject`, and `_.some`.
<br>
<br>
The guarded methods are:<br>
`ary`, `chunk`, `curry`, `curryRight`, `drop`, `dropRight`, `every`,
`fill`, `invert`, `parseInt`, `random`, `range`, `rangeRight`, `repeat`,
`sampleSize`, `slice`, `some`, `sortBy`, `split`, `take`, `takeRight`,
`template`, `trim`, `trimEnd`, `trimStart`, and `words`

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the new mapped array.

#### Example
```js
function square(n) {
  return n * n;
}

_.map([4, 8], square);
// => [16, 64]

_.map({ 'a': 4, 'b': 8 }, square);
// => [16, 64] (iteration order is not guaranteed)

var users = [
  { 'user': 'barney' },
  { 'user': 'fred' }
];

// The `_.property` iteratee shorthand.
_.map(users, 'user');
// => ['barney', 'fred']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_orderbycollection-iteratees_identity-orders"><code>_.orderBy(collection, [iteratees=[_.identity]], [orders])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9603 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.orderby "See the npm package") [&#x24C9;][1]

This method is like `_.sortBy` except that it allows specifying the sort
orders of the iteratees to sort by. If `orders` is unspecified, all values
are sorted in ascending order. Otherwise, specify an order of "desc" for
descending or "asc" for ascending sort order of corresponding values.

#### Since
4.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratees=[_.identity]]` *(Array&#91;&#93;|Function&#91;&#93;|Object&#91;&#93;|string&#91;&#93;)*: The iteratees to sort by.
3. `[orders]` *(string&#91;&#93;)*: The sort orders of `iteratees`.

#### Returns
*(Array)*: Returns the new sorted array.

#### Example
```js
var users = [
  { 'user': 'fred',   'age': 48 },
  { 'user': 'barney', 'age': 34 },
  { 'user': 'fred',   'age': 40 },
  { 'user': 'barney', 'age': 36 }
];

// Sort by `user` in ascending order and by `age` in descending order.
_.orderBy(users, ['user', 'age'], ['asc', 'desc']);
// => objects for [['barney', 36], ['barney', 34], ['fred', 48], ['fred', 40]]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_partitioncollection-predicate_identity"><code>_.partition(collection, [predicate=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9653 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.partition "See the npm package") [&#x24C9;][1]

Creates an array of elements split into two groups, the first of which
contains elements `predicate` returns truthy for, the second of which
contains elements `predicate` returns falsey for. The predicate is
invoked with one argument: *(value)*.

#### Since
3.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the array of grouped elements.

#### Example
```js
var users = [
  { 'user': 'barney',  'age': 36, 'active': false },
  { 'user': 'fred',    'age': 40, 'active': true },
  { 'user': 'pebbles', 'age': 1,  'active': false }
];

_.partition(users, function(o) { return o.active; });
// => objects for [['fred'], ['barney', 'pebbles']]

// The `_.matches` iteratee shorthand.
_.partition(users, { 'age': 1, 'active': false });
// => objects for [['pebbles'], ['barney', 'fred']]

// The `_.matchesProperty` iteratee shorthand.
_.partition(users, ['active', false]);
// => objects for [['barney', 'pebbles'], ['fred']]

// The `_.property` iteratee shorthand.
_.partition(users, 'active');
// => objects for [['fred'], ['barney', 'pebbles']]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_reducecollection-iteratee_identity-accumulator"><code>_.reduce(collection, [iteratee=_.identity], [accumulator])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9694 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.reduce "See the npm package") [&#x24C9;][1]

Reduces `collection` to a value which is the accumulated result of running
each element in `collection` thru `iteratee`, where each successive
invocation is supplied the return value of the previous. If `accumulator`
is not given, the first element of `collection` is used as the initial
value. The iteratee is invoked with four arguments:<br>
*(accumulator, value, index|key, collection)*.
<br>
<br>
Many lodash methods are guarded to work as iteratees for methods like
`_.reduce`, `_.reduceRight`, and `_.transform`.
<br>
<br>
The guarded methods are:<br>
`assign`, `defaults`, `defaultsDeep`, `includes`, `merge`, `orderBy`,
and `sortBy`

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.
3. `[accumulator]` *(&#42;)*: The initial value.

#### Returns
*(&#42;)*: Returns the accumulated value.

#### Example
```js
_.reduce([1, 2], function(sum, n) {
  return sum + n;
}, 0);
// => 3

_.reduce({ 'a': 1, 'b': 2, 'c': 1 }, function(result, value, key) {
  (result[value] || (result[value] = [])).push(key);
  return result;
}, {});
// => { '1': ['a', 'c'], '2': ['b'] } (iteration order is not guaranteed)
```
---

<!-- /div -->

<!-- div -->

<h3 id="_reducerightcollection-iteratee_identity-accumulator"><code>_.reduceRight(collection, [iteratee=_.identity], [accumulator])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9723 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.reduceright "See the npm package") [&#x24C9;][1]

This method is like `_.reduce` except that it iterates over elements of
`collection` from right to left.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratee=_.identity]` *(Function)*: The function invoked per iteration.
3. `[accumulator]` *(&#42;)*: The initial value.

#### Returns
*(&#42;)*: Returns the accumulated value.

#### Example
```js
var array = [[0, 1], [2, 3], [4, 5]];

_.reduceRight(array, function(flattened, other) {
  return flattened.concat(other);
}, []);
// => [4, 5, 2, 3, 0, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_rejectcollection-predicate_identity"><code>_.reject(collection, [predicate=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9764 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.reject "See the npm package") [&#x24C9;][1]

The opposite of `_.filter`; this method returns the elements of `collection`
that `predicate` does **not** return truthy for.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the new filtered array.

#### Example
```js
var users = [
  { 'user': 'barney', 'age': 36, 'active': false },
  { 'user': 'fred',   'age': 40, 'active': true }
];

_.reject(users, function(o) { return !o.active; });
// => objects for ['fred']

// The `_.matches` iteratee shorthand.
_.reject(users, { 'age': 40, 'active': true });
// => objects for ['barney']

// The `_.matchesProperty` iteratee shorthand.
_.reject(users, ['active', false]);
// => objects for ['fred']

// The `_.property` iteratee shorthand.
_.reject(users, 'active');
// => objects for ['barney']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_samplecollection"><code>_.sample(collection)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9783 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sample "See the npm package") [&#x24C9;][1]

Gets a random element from `collection`.

#### Since
2.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to sample.

#### Returns
*(&#42;)*: Returns the random element.

#### Example
```js
_.sample([1, 2, 3, 4]);
// => 2
```
---

<!-- /div -->

<!-- div -->

<h3 id="_samplesizecollection-n1"><code>_.sampleSize(collection, [n=1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9808 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.samplesize "See the npm package") [&#x24C9;][1]

Gets `n` random elements at unique keys from `collection` up to the
size of `collection`.

#### Since
4.0.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to sample.
2. `[n=1]` *(number)*: The number of elements to sample.

#### Returns
*(Array)*: Returns the random elements.

#### Example
```js
_.sampleSize([1, 2, 3], 2);
// => [3, 1]

_.sampleSize([1, 2, 3], 4);
// => [2, 3, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_shufflecollection"><code>_.shuffle(collection)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9833 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.shuffle "See the npm package") [&#x24C9;][1]

Creates an array of shuffled values, using a version of the
[Fisher-Yates shuffle](https://en.wikipedia.org/wiki/Fisher-Yates_shuffle).

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to shuffle.

#### Returns
*(Array)*: Returns the new shuffled array.

#### Example
```js
_.shuffle([1, 2, 3, 4]);
// => [4, 1, 3, 2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sizecollection"><code>_.size(collection)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9859 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.size "See the npm package") [&#x24C9;][1]

Gets the size of `collection` by returning its length for array-like
values or the number of own enumerable string keyed properties for objects.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object|string)*: The collection to inspect.

#### Returns
*(number)*: Returns the collection size.

#### Example
```js
_.size([1, 2, 3]);
// => 3

_.size({ 'a': 1, 'b': 2 });
// => 2

_.size('pebbles');
// => 7
```
---

<!-- /div -->

<!-- div -->

<h3 id="_somecollection-predicate_identity"><code>_.some(collection, [predicate=_.identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9909 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.some "See the npm package") [&#x24C9;][1]

Checks if `predicate` returns truthy for **any** element of `collection`.
Iteration is stopped once `predicate` returns truthy. The predicate is
invoked with three arguments: *(value, index|key, collection)*.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(boolean)*: Returns `true` if any element passes the predicate check, else `false`.

#### Example
```js
_.some([null, 0, 'yes', false], Boolean);
// => true

var users = [
  { 'user': 'barney', 'active': true },
  { 'user': 'fred',   'active': false }
];

// The `_.matches` iteratee shorthand.
_.some(users, { 'user': 'barney', 'active': false });
// => false

// The `_.matchesProperty` iteratee shorthand.
_.some(users, ['active', false]);
// => true

// The `_.property` iteratee shorthand.
_.some(users, 'active');
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sortbycollection-iteratees_identity"><code>_.sortBy(collection, [iteratees=[_.identity]])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L9946 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortby "See the npm package") [&#x24C9;][1]

Creates an array of elements, sorted in ascending order by the results of
running each element in a collection thru each iteratee. This method
performs a stable sort, that is, it preserves the original sort order of
equal elements. The iteratees are invoked with one argument: *(value)*.

#### Since
0.1.0

#### Arguments
1. `collection` *(Array|Object)*: The collection to iterate over.
2. `[iteratees=[_.identity]]` *(...(Function|Function&#91;&#93;))*: The iteratees to sort by.

#### Returns
*(Array)*: Returns the new sorted array.

#### Example
```js
var users = [
  { 'user': 'fred',   'age': 48 },
  { 'user': 'barney', 'age': 36 },
  { 'user': 'fred',   'age': 40 },
  { 'user': 'barney', 'age': 34 }
];

_.sortBy(users, [function(o) { return o.user; }]);
// => objects for [['barney', 36], ['barney', 34], ['fred', 48], ['fred', 40]]

_.sortBy(users, ['user', 'age']);
// => objects for [['barney', 34], ['barney', 36], ['fred', 40], ['fred', 48]]
```
---