# `“Array” Methods` （“数组”方法）

-   <a href="#_chunkarray-size1">`_.chunk`</a>
-   <a href="#_compactarray">`_.compact`</a>
-   <a href="#_concatarray-values">`_.concat`</a>
-   <a href="#_differencearray-values">`_.difference`</a>
-   <a href="#_differencebyarray-values-iteratee_identity">`_.differenceBy`</a>
-   <a href="#_differencewitharray-values-comparator">`_.differenceWith`</a>
-   <a href="#_droparray-n1">`_.drop`</a>
-   <a href="#_droprightarray-n1">`_.dropRight`</a>
-   <a href="#_droprightwhilearray-predicate_identity">`_.dropRightWhile`</a>
-   <a href="#_dropwhilearray-predicate_identity">`_.dropWhile`</a>
-   <a href="#_fillarray-value-start0-endarraylength">`_.fill`</a>
-   <a href="#_findindexarray-predicate_identity-fromindex0">`_.findIndex`</a>
-   <a href="#_findlastindexarray-predicate_identity-fromindexarraylength-1">`_.findLastIndex`</a>
-   <a href="#_headarray" class="alias">`_.first` -> `head`</a>
-   <a href="#_flattenarray">`_.flatten`</a>
-   <a href="#_flattendeeparray">`_.flattenDeep`</a>
-   <a href="#_flattendeptharray-depth1">`_.flattenDepth`</a>
-   <a href="#_frompairspairs">`_.fromPairs`</a>
-   <a href="#_headarray">`_.head`</a>
-   <a href="#_indexofarray-value-fromindex0">`_.indexOf`</a>
-   <a href="#_initialarray">`_.initial`</a>
-   <a href="#_intersectionarrays">`_.intersection`</a>
-   <a href="#_intersectionbyarrays-iteratee_identity">`_.intersectionBy`</a>
-   <a href="#_intersectionwitharrays-comparator">`_.intersectionWith`</a>
-   <a href="#_joinarray-separator-">`_.join`</a>
-   <a href="#_lastarray">`_.last`</a>
-   <a href="#_lastindexofarray-value-fromindexarraylength-1">`_.lastIndexOf`</a>
-   <a href="#_ntharray-n0">`_.nth`</a>
-   <a href="#_pullarray-values">`_.pull`</a>
-   <a href="#_pullallarray-values">`_.pullAll`</a>
-   <a href="#_pullallbyarray-values-iteratee_identity">`_.pullAllBy`</a>
-   <a href="#_pullallwitharray-values-comparator">`_.pullAllWith`</a>
-   <a href="#_pullatarray-indexes">`_.pullAt`</a>
-   <a href="#_removearray-predicate_identity">`_.remove`</a>
-   <a href="#_reversearray">`_.reverse`</a>
-   <a href="#_slicearray-start0-endarraylength">`_.slice`</a>
-   <a href="#_sortedindexarray-value">`_.sortedIndex`</a>
-   <a href="#_sortedindexbyarray-value-iteratee_identity">`_.sortedIndexBy`</a>
-   <a href="#_sortedindexofarray-value">`_.sortedIndexOf`</a>
-   <a href="#_sortedlastindexarray-value">`_.sortedLastIndex`</a>
-   <a href="#_sortedlastindexbyarray-value-iteratee_identity">`_.sortedLastIndexBy`</a>
-   <a href="#_sortedlastindexofarray-value">`_.sortedLastIndexOf`</a>
-   <a href="#_sorteduniqarray">`_.sortedUniq`</a>
-   <a href="#_sorteduniqbyarray-iteratee">`_.sortedUniqBy`</a>
-   <a href="#_tailarray">`_.tail`</a>
-   <a href="#_takearray-n1">`_.take`</a>
-   <a href="#_takerightarray-n1">`_.takeRight`</a>
-   <a href="#_takerightwhilearray-predicate_identity">`_.takeRightWhile`</a>
-   <a href="#_takewhilearray-predicate_identity">`_.takeWhile`</a>
-   <a href="#_unionarrays">`_.union`</a>
-   <a href="#_unionbyarrays-iteratee_identity">`_.unionBy`</a>
-   <a href="#_unionwitharrays-comparator">`_.unionWith`</a>
-   <a href="#_uniqarray">`_.uniq`</a>
-   <a href="#_uniqbyarray-iteratee_identity">`_.uniqBy`</a>
-   <a href="#_uniqwitharray-comparator">`_.uniqWith`</a>
-   <a href="#_unziparray">`_.unzip`</a>
-   <a href="#_unzipwitharray-iteratee_identity">`_.unzipWith`</a>
-   <a href="#_withoutarray-values">`_.without`</a>
-   <a href="#_xorarrays">`_.xor`</a>
-   <a href="#_xorbyarrays-iteratee_identity">`_.xorBy`</a>
-   <a href="#_xorwitharrays-comparator">`_.xorWith`</a>
-   <a href="#_ziparrays">`_.zip`</a>
-   <a href="#_zipobjectprops-values">`_.zipObject`</a>
-   <a href="#_zipobjectdeepprops-values">`_.zipObjectDeep`</a>
-   <a href="#_zipwitharrays-iteratee_identity">`_.zipWith`</a>

---------------------------

<h2 id="_chunkarray-size1">_.chunk(array, [size=1])</h2>


### 相关源码

```js

	/**
     * 将一个数组按照指定size长度拆分，并组成一个新数组
     * 如果数组不能被均匀的分配，那么最后剩余的元素将组成一个块
     *
     * @static
     * @memberOf _
     * @since 3.0.0
     * @category Array
     * @param {Array} array 需要被处理的数组.
     * @param {number} [size=1] 每个区块的大小
     * @param- {Object} [guard] 允许被如`_.map`等方法作为迭代器使用
     * @returns {Array} Returns the new array of chunks.
     * @example
     *
     * _.chunk(['a', 'b', 'c', 'd'], 2);
     * // => [['a', 'b'], ['c', 'd']]
     *
     * _.chunk(['a', 'b', 'c', 'd'], 3);
     * // => [['a', 'b', 'c'], ['d']]
     */
    function chunk(array, size, guard) {
      if ((guard ? isIterateeCall(array, size, guard) : size === undefined)) {
        size = 1;
      } else {
        size = nativeMax(toInteger(size), 0);
      }
      var length = array == null ? 0 : array.length;
      if (!length || size < 1) {
        return [];
      }
      var index = 0,
          resIndex = 0,
          result = Array(nativeCeil(length / size));

      while (index < length) {
        result[resIndex++] = baseSlice(array, index, (index += size));
      }
      return result;
    }

```








Creates an array of elements split into groups the length of `size`.
If `array` can't be split evenly, the final chunk will be the remaining
elements.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to process.
2. `[size=1]` *(number)*: The length of each chunk

#### Returns
*(Array)*: Returns the new array of chunks.

#### Example
```js
_.chunk(['a', 'b', 'c', 'd'], 2);
// => [['a', 'b'], ['c', 'd']]

_.chunk(['a', 'b', 'c', 'd'], 3);
// => [['a', 'b', 'c'], ['d']]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_compactarray">_.compact(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L6891 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.compact "See the npm package") [&#x24C9;][1]

Creates an array with all falsey values removed. The values `false`, `null`,
`0`, `""`, `undefined`, and `NaN` are falsey.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to compact.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
_.compact([0, 1, false, 2, '', 3]);
// => [1, 2, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_concatarray-values">_.concat(array, [values])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L6928 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.concat "See the npm package") [&#x24C9;][1]

Creates a new array concatenating `array` with any additional arrays
and/or values.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to concatenate.
2. `[values]` *(...&#42;)*: The values to concatenate.

#### Returns
*(Array)*: Returns the new concatenated array.

#### Example
```js
var array = [1];
var other = _.concat(array, 2, [3], [[4]]);

console.log(other);
// => [1, 2, 3, [4]]

console.log(array);
// => [1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_differencearray-values">_.difference(array, [values])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L6964 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.difference "See the npm package") [&#x24C9;][1]

Creates an array of `array` values not included in the other given arrays
using [`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons. The order and references of result values are
determined by the first array.
<br>
<br>
**Note:** Unlike `_.pullAll`, this method returns a new array.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[values]` *(...Array)*: The values to exclude.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
_.difference([2, 1], [2, 3]);
// => [1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_differencebyarray-values-iteratee_identity">_.differenceBy(array, [values], [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L6996 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.differenceby "See the npm package") [&#x24C9;][1]

This method is like `_.difference` except that it accepts `iteratee` which
is invoked for each element of `array` and `values` to generate the criterion
by which they're compared. The order and references of result values are
determined by the first array. The iteratee is invoked with one argument:<br>
*(value)*.
<br>
<br>
**Note:** Unlike `_.pullAllBy`, this method returns a new array.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[values]` *(...Array)*: The values to exclude.
3. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
_.differenceBy([2.1, 1.2], [2.3, 3.4], Math.floor);
// => [1.2]

// The `_.property` iteratee shorthand.
_.differenceBy([{ 'x': 2 }, { 'x': 1 }], [{ 'x': 1 }], 'x');
// => [{ 'x': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_differencewitharray-values-comparator">_.differenceWith(array, [values], [comparator])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7029 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.differencewith "See the npm package") [&#x24C9;][1]

This method is like `_.difference` except that it accepts `comparator`
which is invoked to compare elements of `array` to `values`. The order and
references of result values are determined by the first array. The comparator
is invoked with two arguments: *(arrVal, othVal)*.
<br>
<br>
**Note:** Unlike `_.pullAllWith`, this method returns a new array.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[values]` *(...Array)*: The values to exclude.
3. `[comparator]` *(Function)*: The comparator invoked per element.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
var objects = [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }];

_.differenceWith(objects, [{ 'x': 1, 'y': 2 }], _.isEqual);
// => [{ 'x': 2, 'y': 1 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_droparray-n1">_.drop(array, [n=1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7064 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.drop "See the npm package") [&#x24C9;][1]

Creates a slice of `array` with `n` elements dropped from the beginning.

#### Since
0.5.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[n=1]` *(number)*: The number of elements to drop.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
_.drop([1, 2, 3]);
// => [2, 3]

_.drop([1, 2, 3], 2);
// => [3]

_.drop([1, 2, 3], 5);
// => []

_.drop([1, 2, 3], 0);
// => [1, 2, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_droprightarray-n1">_.dropRight(array, [n=1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7098 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.dropright "See the npm package") [&#x24C9;][1]

Creates a slice of `array` with `n` elements dropped from the end.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[n=1]` *(number)*: The number of elements to drop.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
_.dropRight([1, 2, 3]);
// => [1, 2]

_.dropRight([1, 2, 3], 2);
// => [1]

_.dropRight([1, 2, 3], 5);
// => []

_.dropRight([1, 2, 3], 0);
// => [1, 2, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_droprightwhilearray-predicate_identity">_.dropRightWhile(array, [predicate=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7143 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.droprightwhile "See the npm package") [&#x24C9;][1]

Creates a slice of `array` excluding elements dropped from the end.
Elements are dropped until `predicate` returns falsey. The predicate is
invoked with three arguments: *(value, index, array)*.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
var users = [
  { 'user': 'barney',  'active': true },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': false }
];

_.dropRightWhile(users, function(o) { return !o.active; });
// => objects for ['barney']

// The `_.matches` iteratee shorthand.
_.dropRightWhile(users, { 'user': 'pebbles', 'active': false });
// => objects for ['barney', 'fred']

// The `_.matchesProperty` iteratee shorthand.
_.dropRightWhile(users, ['active', false]);
// => objects for ['barney']

// The `_.property` iteratee shorthand.
_.dropRightWhile(users, 'active');
// => objects for ['barney', 'fred', 'pebbles']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_dropwhilearray-predicate_identity">_.dropWhile(array, [predicate=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7184 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.dropwhile "See the npm package") [&#x24C9;][1]

Creates a slice of `array` excluding elements dropped from the beginning.
Elements are dropped until `predicate` returns falsey. The predicate is
invoked with three arguments: *(value, index, array)*.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
var users = [
  { 'user': 'barney',  'active': false },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': true }
];

_.dropWhile(users, function(o) { return !o.active; });
// => objects for ['pebbles']

// The `_.matches` iteratee shorthand.
_.dropWhile(users, { 'user': 'barney', 'active': false });
// => objects for ['fred', 'pebbles']

// The `_.matchesProperty` iteratee shorthand.
_.dropWhile(users, ['active', false]);
// => objects for ['pebbles']

// The `_.property` iteratee shorthand.
_.dropWhile(users, 'active');
// => objects for ['barney', 'fred', 'pebbles']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_fillarray-value-start0-endarraylength">_.fill(array, value, [start=0], [end=array.length])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7219 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.fill "See the npm package") [&#x24C9;][1]

Fills elements of `array` with `value` from `start` up to, but not
including, `end`.
<br>
<br>
**Note:** This method mutates `array`.

#### Since
3.2.0

#### Arguments
1. `array` *(Array)*: The array to fill.
2. `value` *(&#42;)*: The value to fill `array` with.
3. `[start=0]` *(number)*: The start position.
4. `[end=array.length]` *(number)*: The end position.

#### Returns
*(Array)*: Returns `array`.

#### Example
```js
var array = [1, 2, 3];

_.fill(array, 'a');
console.log(array);
// => ['a', 'a', 'a']

_.fill(Array(3), 2);
// => [2, 2, 2]

_.fill([4, 6, 8, 10], '*', 1, 3);
// => [4, '*', '*', 10]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_findindexarray-predicate_identity-fromindex0">_.findIndex(array, [predicate=_.identity], [fromIndex=0])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7266 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.findindex "See the npm package") [&#x24C9;][1]

This method is like `_.find` except that it returns the index of the first
element `predicate` returns truthy for instead of the element itself.

#### Since
1.1.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.
3. `[fromIndex=0]` *(number)*: The index to search from.

#### Returns
*(number)*: Returns the index of the found element, else `-1`.

#### Example
```js
var users = [
  { 'user': 'barney',  'active': false },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': true }
];

_.findIndex(users, function(o) { return o.user == 'barney'; });
// => 0

// The `_.matches` iteratee shorthand.
_.findIndex(users, { 'user': 'fred', 'active': false });
// => 1

// The `_.matchesProperty` iteratee shorthand.
_.findIndex(users, ['active', false]);
// => 0

// The `_.property` iteratee shorthand.
_.findIndex(users, 'active');
// => 2
```
---

<!-- /div -->

<!-- div -->

<h3 id="_findlastindexarray-predicate_identity-fromindexarraylength-1">_.findLastIndex(array, [predicate=_.identity], [fromIndex=array.length-1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7313 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.findlastindex "See the npm package") [&#x24C9;][1]

This method is like `_.findIndex` except that it iterates over elements
of `collection` from right to left.

#### Since
2.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.
3. `[fromIndex=array.length-1]` *(number)*: The index to search from.

#### Returns
*(number)*: Returns the index of the found element, else `-1`.

#### Example
```js
var users = [
  { 'user': 'barney',  'active': true },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': false }
];

_.findLastIndex(users, function(o) { return o.user == 'pebbles'; });
// => 2

// The `_.matches` iteratee shorthand.
_.findLastIndex(users, { 'user': 'barney', 'active': true });
// => 0

// The `_.matchesProperty` iteratee shorthand.
_.findLastIndex(users, ['active', false]);
// => 2

// The `_.property` iteratee shorthand.
_.findLastIndex(users, 'active');
// => 0
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flattenarray">_.flatten(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7342 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flatten "See the npm package") [&#x24C9;][1]

Flattens `array` a single level deep.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to flatten.

#### Returns
*(Array)*: Returns the new flattened array.

#### Example
```js
_.flatten([1, [2, [3, [4]], 5]]);
// => [1, 2, [3, [4]], 5]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flattendeeparray">_.flattenDeep(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7361 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flattendeep "See the npm package") [&#x24C9;][1]

Recursively flattens `array`.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to flatten.

#### Returns
*(Array)*: Returns the new flattened array.

#### Example
```js
_.flattenDeep([1, [2, [3, [4]], 5]]);
// => [1, 2, 3, 4, 5]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flattendeptharray-depth1">_.flattenDepth(array, [depth=1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7386 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flattendepth "See the npm package") [&#x24C9;][1]

Recursively flatten `array` up to `depth` times.

#### Since
4.4.0

#### Arguments
1. `array` *(Array)*: The array to flatten.
2. `[depth=1]` *(number)*: The maximum recursion depth.

#### Returns
*(Array)*: Returns the new flattened array.

#### Example
```js
var array = [1, [2, [3, [4]], 5]];

_.flattenDepth(array, 1);
// => [1, 2, [3, [4]], 5]

_.flattenDepth(array, 2);
// => [1, 2, 3, [4], 5]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_frompairspairs">_.fromPairs(pairs)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7410 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.frompairs "See the npm package") [&#x24C9;][1]

The inverse of `_.toPairs`; this method returns an object composed
from key-value `pairs`.

#### Since
4.0.0

#### Arguments
1. `pairs` *(Array)*: The key-value pairs.

#### Returns
*(Object)*: Returns the new object.

#### Example
```js
_.fromPairs([['a', 1], ['b', 2]]);
// => { 'a': 1, 'b': 2 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_headarray">_.head(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7440 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.head "See the npm package") [&#x24C9;][1]

Gets the first element of `array`.

#### Since
0.1.0

#### Aliases
*_.first*

#### Arguments
1. `array` *(Array)*: The array to query.

#### Returns
*(&#42;)*: Returns the first element of `array`.

#### Example
```js
_.head([1, 2, 3]);
// => 1

_.head([]);
// => undefined
```
---

<!-- /div -->

<!-- div -->

<h3 id="_indexofarray-value-fromindex0">_.indexOf(array, value, [fromIndex=0])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7467 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.indexof "See the npm package") [&#x24C9;][1]

Gets the index at which the first occurrence of `value` is found in `array`
using [`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons. If `fromIndex` is negative, it's used as the
offset from the end of `array`.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `value` *(&#42;)*: The value to search for.
3. `[fromIndex=0]` *(number)*: The index to search from.

#### Returns
*(number)*: Returns the index of the matched value, else `-1`.

#### Example
```js
_.indexOf([1, 2, 1, 2], 2);
// => 1

// Search from the `fromIndex`.
_.indexOf([1, 2, 1, 2], 2, 2);
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_initialarray">_.initial(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7493 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.initial "See the npm package") [&#x24C9;][1]

Gets all but the last element of `array`.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to query.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
_.initial([1, 2, 3]);
// => [1, 2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_intersectionarrays">_.intersection([arrays])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7515 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.intersection "See the npm package") [&#x24C9;][1]

Creates an array of unique values that are included in all given arrays
using [`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons. The order and references of result values are
determined by the first array.

#### Since
0.1.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.

#### Returns
*(Array)*: Returns the new array of intersecting values.

#### Example
```js
_.intersection([2, 1], [2, 3]);
// => [2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_intersectionbyarrays-iteratee_identity">_.intersectionBy([arrays], [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7545 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.intersectionby "See the npm package") [&#x24C9;][1]

This method is like `_.intersection` except that it accepts `iteratee`
which is invoked for each element of each `arrays` to generate the criterion
by which they're compared. The order and references of result values are
determined by the first array. The iteratee is invoked with one argument:<br>
*(value)*.

#### Since
4.0.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns the new array of intersecting values.

#### Example
```js
_.intersectionBy([2.1, 1.2], [2.3, 3.4], Math.floor);
// => [2.1]

// The `_.property` iteratee shorthand.
_.intersectionBy([{ 'x': 1 }], [{ 'x': 2 }, { 'x': 1 }], 'x');
// => [{ 'x': 1 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_intersectionwitharrays-comparator">_.intersectionWith([arrays], [comparator])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7580 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.intersectionwith "See the npm package") [&#x24C9;][1]

This method is like `_.intersection` except that it accepts `comparator`
which is invoked to compare elements of `arrays`. The order and references
of result values are determined by the first array. The comparator is
invoked with two arguments: *(arrVal, othVal)*.

#### Since
4.0.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.
2. `[comparator]` *(Function)*: The comparator invoked per element.

#### Returns
*(Array)*: Returns the new array of intersecting values.

#### Example
```js
var objects = [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }];
var others = [{ 'x': 1, 'y': 1 }, { 'x': 1, 'y': 2 }];

_.intersectionWith(objects, others, _.isEqual);
// => [{ 'x': 1, 'y': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_joinarray-separator-">_.join(array, [separator=','])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7608 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.join "See the npm package") [&#x24C9;][1]

Converts all elements in `array` into a string separated by `separator`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to convert.
2. `[separator=',']` *(string)*: The element separator.

#### Returns
*(string)*: Returns the joined string.

#### Example
```js
_.join(['a', 'b', 'c'], '~');
// => 'a~b~c'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_lastarray">_.last(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7626 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.last "See the npm package") [&#x24C9;][1]

Gets the last element of `array`.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to query.

#### Returns
*(&#42;)*: Returns the last element of `array`.

#### Example
```js
_.last([1, 2, 3]);
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_lastindexofarray-value-fromindexarraylength-1">_.lastIndexOf(array, value, [fromIndex=array.length-1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7652 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.lastindexof "See the npm package") [&#x24C9;][1]

This method is like `_.indexOf` except that it iterates over elements of
`array` from right to left.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `value` *(&#42;)*: The value to search for.
3. `[fromIndex=array.length-1]` *(number)*: The index to search from.

#### Returns
*(number)*: Returns the index of the matched value, else `-1`.

#### Example
```js
_.lastIndexOf([1, 2, 1, 2], 2);
// => 3

// Search from the `fromIndex`.
_.lastIndexOf([1, 2, 1, 2], 2, 2);
// => 1
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ntharray-n0">_.nth(array, [n=0])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7688 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.nth "See the npm package") [&#x24C9;][1]

Gets the element at index `n` of `array`. If `n` is negative, the nth
element from the end is returned.

#### Since
4.11.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[n=0]` *(number)*: The index of the element to return.

#### Returns
*(&#42;)*: Returns the nth element of `array`.

#### Example
```js
var array = ['a', 'b', 'c', 'd'];

_.nth(array, 1);
// => 'b'

_.nth(array, -2);
// => 'c';
```
---

<!-- /div -->

<!-- div -->

<h3 id="_pullarray-values">_.pull(array, [values])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7715 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.pull "See the npm package") [&#x24C9;][1]

Removes all given values from `array` using
[`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons.
<br>
<br>
**Note:** Unlike `_.without`, this method mutates `array`. Use `_.remove`
to remove elements from an array by predicate.

#### Since
2.0.0

#### Arguments
1. `array` *(Array)*: The array to modify.
2. `[values]` *(...&#42;)*: The values to remove.

#### Returns
*(Array)*: Returns `array`.

#### Example
```js
var array = ['a', 'b', 'c', 'a', 'b', 'c'];

_.pull(array, 'a', 'c');
console.log(array);
// => ['b', 'b']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_pullallarray-values">_.pullAll(array, values)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7737 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.pullall "See the npm package") [&#x24C9;][1]

This method is like `_.pull` except that it accepts an array of values to remove.
<br>
<br>
**Note:** Unlike `_.difference`, this method mutates `array`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to modify.
2. `values` *(Array)*: The values to remove.

#### Returns
*(Array)*: Returns `array`.

#### Example
```js
var array = ['a', 'b', 'c', 'a', 'b', 'c'];

_.pullAll(array, ['a', 'c']);
console.log(array);
// => ['b', 'b']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_pullallbyarray-values-iteratee_identity">_.pullAllBy(array, values, [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7766 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.pullallby "See the npm package") [&#x24C9;][1]

This method is like `_.pullAll` except that it accepts `iteratee` which is
invoked for each element of `array` and `values` to generate the criterion
by which they're compared. The iteratee is invoked with one argument: *(value)*.
<br>
<br>
**Note:** Unlike `_.differenceBy`, this method mutates `array`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to modify.
2. `values` *(Array)*: The values to remove.
3. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns `array`.

#### Example
```js
var array = [{ 'x': 1 }, { 'x': 2 }, { 'x': 3 }, { 'x': 1 }];

_.pullAllBy(array, [{ 'x': 1 }, { 'x': 3 }], 'x');
console.log(array);
// => [{ 'x': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_pullallwitharray-values-comparator">_.pullAllWith(array, values, [comparator])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7795 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.pullallwith "See the npm package") [&#x24C9;][1]

This method is like `_.pullAll` except that it accepts `comparator` which
is invoked to compare elements of `array` to `values`. The comparator is
invoked with two arguments: *(arrVal, othVal)*.
<br>
<br>
**Note:** Unlike `_.differenceWith`, this method mutates `array`.

#### Since
4.6.0

#### Arguments
1. `array` *(Array)*: The array to modify.
2. `values` *(Array)*: The values to remove.
3. `[comparator]` *(Function)*: The comparator invoked per element.

#### Returns
*(Array)*: Returns `array`.

#### Example
```js
var array = [{ 'x': 1, 'y': 2 }, { 'x': 3, 'y': 4 }, { 'x': 5, 'y': 6 }];

_.pullAllWith(array, [{ 'x': 3, 'y': 4 }], _.isEqual);
console.log(array);
// => [{ 'x': 1, 'y': 2 }, { 'x': 5, 'y': 6 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_pullatarray-indexes">_.pullAt(array, [indexes])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7825 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.pullat "See the npm package") [&#x24C9;][1]

Removes elements from `array` corresponding to `indexes` and returns an
array of removed elements.
<br>
<br>
**Note:** Unlike `_.at`, this method mutates `array`.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to modify.
2. `[indexes]` *(...(number|number&#91;&#93;))*: The indexes of elements to remove.

#### Returns
*(Array)*: Returns the new array of removed elements.

#### Example
```js
var array = ['a', 'b', 'c', 'd'];
var pulled = _.pullAt(array, [1, 3]);

console.log(array);
// => ['a', 'c']

console.log(pulled);
// => ['b', 'd']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_removearray-predicate_identity">_.remove(array, [predicate=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7864 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.remove "See the npm package") [&#x24C9;][1]

Removes all elements from `array` that `predicate` returns truthy for
and returns an array of the removed elements. The predicate is invoked
with three arguments: *(value, index, array)*.
<br>
<br>
**Note:** Unlike `_.filter`, this method mutates `array`. Use `_.pull`
to pull elements from an array by value.

#### Since
2.0.0

#### Arguments
1. `array` *(Array)*: The array to modify.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the new array of removed elements.

#### Example
```js
var array = [1, 2, 3, 4];
var evens = _.remove(array, function(n) {
  return n % 2 == 0;
});

console.log(array);
// => [1, 3]

console.log(evens);
// => [2, 4]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_reversearray">_.reverse(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7908 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.reverse "See the npm package") [&#x24C9;][1]

Reverses `array` so that the first element becomes the last, the second
element becomes the second to last, and so on.
<br>
<br>
**Note:** This method mutates `array` and is based on
[`Array#reverse`](https://mdn.io/Array/reverse).

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to modify.

#### Returns
*(Array)*: Returns `array`.

#### Example
```js
var array = [1, 2, 3];

_.reverse(array);
// => [3, 2, 1]

console.log(array);
// => [3, 2, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_slicearray-start0-endarraylength">_.slice(array, [start=0], [end=array.length])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7928 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.slice "See the npm package") [&#x24C9;][1]

Creates a slice of `array` from `start` up to, but not including, `end`.
<br>
<br>
**Note:** This method is used instead of
[`Array#slice`](https://mdn.io/Array/slice) to ensure dense arrays are
returned.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to slice.
2. `[start=0]` *(number)*: The start position.
3. `[end=array.length]` *(number)*: The end position.

#### Returns
*(Array)*: Returns the slice of `array`.

---

<!-- /div -->

<!-- div -->

<h3 id="_sortedindexarray-value">_.sortedIndex(array, value)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7961 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortedindex "See the npm package") [&#x24C9;][1]

Uses a binary search to determine the lowest index at which `value`
should be inserted into `array` in order to maintain its sort order.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The sorted array to inspect.
2. `value` *(&#42;)*: The value to evaluate.

#### Returns
*(number)*: Returns the index at which `value` should be inserted into `array`.

#### Example
```js
_.sortedIndex([30, 50], 40);
// => 1
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sortedindexbyarray-value-iteratee_identity">_.sortedIndexBy(array, value, [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L7990 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortedindexby "See the npm package") [&#x24C9;][1]

This method is like `_.sortedIndex` except that it accepts `iteratee`
which is invoked for `value` and each element of `array` to compute their
sort ranking. The iteratee is invoked with one argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The sorted array to inspect.
2. `value` *(&#42;)*: The value to evaluate.
3. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(number)*: Returns the index at which `value` should be inserted into `array`.

#### Example
```js
var objects = [{ 'x': 4 }, { 'x': 5 }];

_.sortedIndexBy(objects, { 'x': 4 }, function(o) { return o.x; });
// => 0

// The `_.property` iteratee shorthand.
_.sortedIndexBy(objects, { 'x': 4 }, 'x');
// => 0
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sortedindexofarray-value">_.sortedIndexOf(array, value)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8010 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortedindexof "See the npm package") [&#x24C9;][1]

This method is like `_.indexOf` except that it performs a binary
search on a sorted `array`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `value` *(&#42;)*: The value to search for.

#### Returns
*(number)*: Returns the index of the matched value, else `-1`.

#### Example
```js
_.sortedIndexOf([4, 5, 5, 5, 6], 5);
// => 1
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sortedlastindexarray-value">_.sortedLastIndex(array, value)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8039 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortedlastindex "See the npm package") [&#x24C9;][1]

This method is like `_.sortedIndex` except that it returns the highest
index at which `value` should be inserted into `array` in order to
maintain its sort order.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The sorted array to inspect.
2. `value` *(&#42;)*: The value to evaluate.

#### Returns
*(number)*: Returns the index at which `value` should be inserted into `array`.

#### Example
```js
_.sortedLastIndex([4, 5, 5, 5, 6], 5);
// => 4
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sortedlastindexbyarray-value-iteratee_identity">_.sortedLastIndexBy(array, value, [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8068 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortedlastindexby "See the npm package") [&#x24C9;][1]

This method is like `_.sortedLastIndex` except that it accepts `iteratee`
which is invoked for `value` and each element of `array` to compute their
sort ranking. The iteratee is invoked with one argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The sorted array to inspect.
2. `value` *(&#42;)*: The value to evaluate.
3. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(number)*: Returns the index at which `value` should be inserted into `array`.

#### Example
```js
var objects = [{ 'x': 4 }, { 'x': 5 }];

_.sortedLastIndexBy(objects, { 'x': 4 }, function(o) { return o.x; });
// => 1

// The `_.property` iteratee shorthand.
_.sortedLastIndexBy(objects, { 'x': 4 }, 'x');
// => 1
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sortedlastindexofarray-value">_.sortedLastIndexOf(array, value)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8088 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sortedlastindexof "See the npm package") [&#x24C9;][1]

This method is like `_.lastIndexOf` except that it performs a binary
search on a sorted `array`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `value` *(&#42;)*: The value to search for.

#### Returns
*(number)*: Returns the index of the matched value, else `-1`.

#### Example
```js
_.sortedLastIndexOf([4, 5, 5, 5, 6], 5);
// => 3
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sorteduniqarray">_.sortedUniq(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8114 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sorteduniq "See the npm package") [&#x24C9;][1]

This method is like `_.uniq` except that it's designed and optimized
for sorted arrays.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.

#### Returns
*(Array)*: Returns the new duplicate free array.

#### Example
```js
_.sortedUniq([1, 1, 2]);
// => [1, 2]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_sorteduniqbyarray-iteratee">_.sortedUniqBy(array, [iteratee])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8136 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.sorteduniqby "See the npm package") [&#x24C9;][1]

This method is like `_.uniqBy` except that it's designed and optimized
for sorted arrays.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[iteratee]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns the new duplicate free array.

#### Example
```js
_.sortedUniqBy([1.1, 1.2, 2.3, 2.4], Math.floor);
// => [1.1, 2.3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tailarray">_.tail(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8156 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tail "See the npm package") [&#x24C9;][1]

Gets all but the first element of `array`.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to query.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
_.tail([1, 2, 3]);
// => [2, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_takearray-n1">_.take(array, [n=1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8186 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.take "See the npm package") [&#x24C9;][1]

Creates a slice of `array` with `n` elements taken from the beginning.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[n=1]` *(number)*: The number of elements to take.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
_.take([1, 2, 3]);
// => [1]

_.take([1, 2, 3], 2);
// => [1, 2]

_.take([1, 2, 3], 5);
// => [1, 2, 3]

_.take([1, 2, 3], 0);
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_takerightarray-n1">_.takeRight(array, [n=1])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8219 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.takeright "See the npm package") [&#x24C9;][1]

Creates a slice of `array` with `n` elements taken from the end.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[n=1]` *(number)*: The number of elements to take.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
_.takeRight([1, 2, 3]);
// => [3]

_.takeRight([1, 2, 3], 2);
// => [2, 3]

_.takeRight([1, 2, 3], 5);
// => [1, 2, 3]

_.takeRight([1, 2, 3], 0);
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_takerightwhilearray-predicate_identity">_.takeRightWhile(array, [predicate=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8264 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.takerightwhile "See the npm package") [&#x24C9;][1]

Creates a slice of `array` with elements taken from the end. Elements are
taken until `predicate` returns falsey. The predicate is invoked with
three arguments: *(value, index, array)*.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
var users = [
  { 'user': 'barney',  'active': true },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': false }
];

_.takeRightWhile(users, function(o) { return !o.active; });
// => objects for ['fred', 'pebbles']

// The `_.matches` iteratee shorthand.
_.takeRightWhile(users, { 'user': 'pebbles', 'active': false });
// => objects for ['pebbles']

// The `_.matchesProperty` iteratee shorthand.
_.takeRightWhile(users, ['active', false]);
// => objects for ['fred', 'pebbles']

// The `_.property` iteratee shorthand.
_.takeRightWhile(users, 'active');
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_takewhilearray-predicate_identity">_.takeWhile(array, [predicate=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8305 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.takewhile "See the npm package") [&#x24C9;][1]

Creates a slice of `array` with elements taken from the beginning. Elements
are taken until `predicate` returns falsey. The predicate is invoked with
three arguments: *(value, index, array)*.

#### Since
3.0.0

#### Arguments
1. `array` *(Array)*: The array to query.
2. `[predicate=_.identity]` *(Function)*: The function invoked per iteration.

#### Returns
*(Array)*: Returns the slice of `array`.

#### Example
```js
var users = [
  { 'user': 'barney',  'active': false },
  { 'user': 'fred',    'active': false },
  { 'user': 'pebbles', 'active': true }
];

_.takeWhile(users, function(o) { return !o.active; });
// => objects for ['barney', 'fred']

// The `_.matches` iteratee shorthand.
_.takeWhile(users, { 'user': 'barney', 'active': false });
// => objects for ['barney']

// The `_.matchesProperty` iteratee shorthand.
_.takeWhile(users, ['active', false]);
// => objects for ['barney', 'fred']

// The `_.property` iteratee shorthand.
_.takeWhile(users, 'active');
// => []
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unionarrays">_.union([arrays])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8327 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.union "See the npm package") [&#x24C9;][1]

Creates an array of unique values, in order, from all given arrays using
[`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons.

#### Since
0.1.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.

#### Returns
*(Array)*: Returns the new array of combined values.

#### Example
```js
_.union([2], [1, 2]);
// => [2, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unionbyarrays-iteratee_identity">_.unionBy([arrays], [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8354 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.unionby "See the npm package") [&#x24C9;][1]

This method is like `_.union` except that it accepts `iteratee` which is
invoked for each element of each `arrays` to generate the criterion by
which uniqueness is computed. Result values are chosen from the first
array in which the value occurs. The iteratee is invoked with one argument:<br>
*(value)*.

#### Since
4.0.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns the new array of combined values.

#### Example
```js
_.unionBy([2.1], [1.2, 2.3], Math.floor);
// => [2.1, 1.2]

// The `_.property` iteratee shorthand.
_.unionBy([{ 'x': 1 }], [{ 'x': 2 }, { 'x': 1 }], 'x');
// => [{ 'x': 1 }, { 'x': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unionwitharrays-comparator">_.unionWith([arrays], [comparator])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8383 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.unionwith "See the npm package") [&#x24C9;][1]

This method is like `_.union` except that it accepts `comparator` which
is invoked to compare elements of `arrays`. Result values are chosen from
the first array in which the value occurs. The comparator is invoked
with two arguments: *(arrVal, othVal)*.

#### Since
4.0.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.
2. `[comparator]` *(Function)*: The comparator invoked per element.

#### Returns
*(Array)*: Returns the new array of combined values.

#### Example
```js
var objects = [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }];
var others = [{ 'x': 1, 'y': 1 }, { 'x': 1, 'y': 2 }];

_.unionWith(objects, others, _.isEqual);
// => [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }, { 'x': 1, 'y': 1 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_uniqarray">_.uniq(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8407 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.uniq "See the npm package") [&#x24C9;][1]

Creates a duplicate-free version of an array, using
[`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons, in which only the first occurrence of each element
is kept. The order of result values is determined by the order they occur
in the array.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to inspect.

#### Returns
*(Array)*: Returns the new duplicate free array.

#### Example
```js
_.uniq([2, 1, 2]);
// => [2, 1]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_uniqbyarray-iteratee_identity">_.uniqBy(array, [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8434 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.uniqby "See the npm package") [&#x24C9;][1]

This method is like `_.uniq` except that it accepts `iteratee` which is
invoked for each element in `array` to generate the criterion by which
uniqueness is computed. The order of result values is determined by the
order they occur in the array. The iteratee is invoked with one argument:<br>
*(value)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns the new duplicate free array.

#### Example
```js
_.uniqBy([2.1, 1.2, 2.3], Math.floor);
// => [2.1, 1.2]

// The `_.property` iteratee shorthand.
_.uniqBy([{ 'x': 1 }, { 'x': 2 }, { 'x': 1 }], 'x');
// => [{ 'x': 1 }, { 'x': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_uniqwitharray-comparator">_.uniqWith(array, [comparator])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8458 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.uniqwith "See the npm package") [&#x24C9;][1]

This method is like `_.uniq` except that it accepts `comparator` which
is invoked to compare elements of `array`. The order of result values is
determined by the order they occur in the array.The comparator is invoked
with two arguments: *(arrVal, othVal)*.

#### Since
4.0.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[comparator]` *(Function)*: The comparator invoked per element.

#### Returns
*(Array)*: Returns the new duplicate free array.

#### Example
```js
var objects = [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }, { 'x': 1, 'y': 2 }];

_.uniqWith(objects, _.isEqual);
// => [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unziparray">_.unzip(array)</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8482 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.unzip "See the npm package") [&#x24C9;][1]

This method is like `_.zip` except that it accepts an array of grouped
elements and creates an array regrouping the elements to their pre-zip
configuration.

#### Since
1.2.0

#### Arguments
1. `array` *(Array)*: The array of grouped elements to process.

#### Returns
*(Array)*: Returns the new array of regrouped elements.

#### Example
```js
var zipped = _.zip(['a', 'b'], [1, 2], [true, false]);
// => [['a', 1, true], ['b', 2, false]]

_.unzip(zipped);
// => [['a', 'b'], [1, 2], [true, false]]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unzipwitharray-iteratee_identity">_.unzipWith(array, [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8519 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.unzipwith "See the npm package") [&#x24C9;][1]

This method is like `_.unzip` except that it accepts `iteratee` to specify
how regrouped values should be combined. The iteratee is invoked with the
elements of each group: *(...group)*.

#### Since
3.8.0

#### Arguments
1. `array` *(Array)*: The array of grouped elements to process.
2. `[iteratee=_.identity]` *(Function)*: The function to combine regrouped values.

#### Returns
*(Array)*: Returns the new array of regrouped elements.

#### Example
```js
var zipped = _.zip([1, 2], [10, 20], [100, 200]);
// => [[1, 10, 100], [2, 20, 200]]

_.unzipWith(zipped, _.add);
// => [3, 30, 300]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_withoutarray-values">_.without(array, [values])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8552 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.without "See the npm package") [&#x24C9;][1]

Creates an array excluding all given values using
[`SameValueZero`](http://ecma-international.org/ecma-262/7.0/#sec-samevaluezero)
for equality comparisons.
<br>
<br>
**Note:** Unlike `_.pull`, this method returns a new array.

#### Since
0.1.0

#### Arguments
1. `array` *(Array)*: The array to inspect.
2. `[values]` *(...&#42;)*: The values to exclude.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
_.without([2, 1, 2, 3], 1, 2);
// => [3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_xorarrays">_.xor([arrays])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8576 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.xor "See the npm package") [&#x24C9;][1]

Creates an array of unique values that is the
[symmetric difference](https://en.wikipedia.org/wiki/Symmetric_difference)
of the given arrays. The order of result values is determined by the order
they occur in the arrays.

#### Since
2.4.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
_.xor([2, 1], [2, 3]);
// => [1, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_xorbyarrays-iteratee_identity">_.xorBy([arrays], [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8603 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.xorby "See the npm package") [&#x24C9;][1]

This method is like `_.xor` except that it accepts `iteratee` which is
invoked for each element of each `arrays` to generate the criterion by
which by which they're compared. The order of result values is determined
by the order they occur in the arrays. The iteratee is invoked with one
argument: *(value)*.

#### Since
4.0.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.
2. `[iteratee=_.identity]` *(Function)*: The iteratee invoked per element.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
_.xorBy([2.1, 1.2], [2.3, 3.4], Math.floor);
// => [1.2, 3.4]

// The `_.property` iteratee shorthand.
_.xorBy([{ 'x': 1 }], [{ 'x': 2 }, { 'x': 1 }], 'x');
// => [{ 'x': 2 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_xorwitharrays-comparator">_.xorWith([arrays], [comparator])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8632 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.xorwith "See the npm package") [&#x24C9;][1]

This method is like `_.xor` except that it accepts `comparator` which is
invoked to compare elements of `arrays`. The order of result values is
determined by the order they occur in the arrays. The comparator is invoked
with two arguments: *(arrVal, othVal)*.

#### Since
4.0.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to inspect.
2. `[comparator]` *(Function)*: The comparator invoked per element.

#### Returns
*(Array)*: Returns the new array of filtered values.

#### Example
```js
var objects = [{ 'x': 1, 'y': 2 }, { 'x': 2, 'y': 1 }];
var others = [{ 'x': 1, 'y': 1 }, { 'x': 1, 'y': 2 }];

_.xorWith(objects, others, _.isEqual);
// => [{ 'x': 2, 'y': 1 }, { 'x': 1, 'y': 1 }]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_ziparrays">_.zip([arrays])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8654 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.zip "See the npm package") [&#x24C9;][1]

Creates an array of grouped elements, the first of which contains the
first elements of the given arrays, the second of which contains the
second elements of the given arrays, and so on.

#### Since
0.1.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to process.

#### Returns
*(Array)*: Returns the new array of grouped elements.

#### Example
```js
_.zip(['a', 'b'], [1, 2], [true, false]);
// => [['a', 1, true], ['b', 2, false]]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_zipobjectprops-values">_.zipObject([props=[]], [values=[]])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8672 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.zipobject "See the npm package") [&#x24C9;][1]

This method is like `_.fromPairs` except that it accepts two arrays,
one of property identifiers and one of corresponding values.

#### Since
0.4.0

#### Arguments
1. `[props=[]]` *(Array)*: The property identifiers.
2. `[values=[]]` *(Array)*: The property values.

#### Returns
*(Object)*: Returns the new object.

#### Example
```js
_.zipObject(['a', 'b'], [1, 2]);
// => { 'a': 1, 'b': 2 }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_zipobjectdeepprops-values">_.zipObjectDeep([props=[]], [values=[]])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8691 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.zipobjectdeep "See the npm package") [&#x24C9;][1]

This method is like `_.zipObject` except that it supports property paths.

#### Since
4.1.0

#### Arguments
1. `[props=[]]` *(Array)*: The property identifiers.
2. `[values=[]]` *(Array)*: The property values.

#### Returns
*(Object)*: Returns the new object.

#### Example
```js
_.zipObjectDeep(['a.b[0].c', 'a.b[1].d'], [1, 2]);
// => { 'a': { 'b': [{ 'c': 1 }, { 'd': 2 }] } }
```
---

<!-- /div -->

<!-- div -->

<h3 id="_zipwitharrays-iteratee_identity">_.zipWith([arrays], [iteratee=_.identity])</h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L8715 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.zipwith "See the npm package") [&#x24C9;][1]

This method is like `_.zip` except that it accepts `iteratee` to specify
how grouped values should be combined. The iteratee is invoked with the
elements of each group: *(...group)*.

#### Since
3.8.0

#### Arguments
1. `[arrays]` *(...Array)*: The arrays to process.
2. `[iteratee=_.identity]` *(Function)*: The function to combine grouped values.

#### Returns
*(Array)*: Returns the new array of grouped elements.

#### Example
```js
_.zipWith([1, 2], [10, 20], [100, 200], function(a, b, c) {
  return a + b + c;
});
// => [111, 222]
```
---

<!-- /div -->

<!-- /div -->

<!-- div -->