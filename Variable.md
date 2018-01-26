# Variable变量


1.

```js
    /** Used as a safe reference for `undefined` in pre-ES5 environments. */
    var undefined;
```
> 注释

    这里定义一个安全的引用，主要为了兼容在ES5之前的JavaScript环境中。在ES5之前是没有Undefined类型的。

-----------

2.

```js

    /** Used as the size to enable large array optimizations. */
    var LARGE_ARRAY_SIZE = 200;

```
> 注释

    定义当数组过大时对数组进行优化的临界值，超过时需要对数组进行优化。

-----------

3.

```js

    /** Used as the maximum memoize cache size. */
    var MAX_MEMOIZE_SIZE = 500;

```
> 注释

    用作最大memoize缓存大小。其中，memoize是一个underscore的一个性能优化函数，可以缓存重复递归运算中的值

> 扩展

```js

    // Memoize an expensive function by storing its results.
    //「记忆化」，存储中间运算结果，提高效率
    // 参数 hasher 是个 function，用来计算 key
    // 如果传入了 hasher，则用 hasher 来计算 key
    // 否则用 key 参数直接当 key（即 memoize 方法传入的第一个参数）
    // _.memoize(function, [hashFunction])
    // 适用于需要大量重复求值的场景
    // 比如递归求解菲波那切数
    // @http://www.jameskrob.com/memoize.html
    // create hash for storing "expensive" function outputs
    // run expensive function
    // check whether function has already been run with given arguments via hash lookup
    // if false - run function, and store output in hash
    // if true, return output stored in hash
    _.memoize = function(func, hasher) {
        var memoize = function(key) {
        var cache = memoize.cache;
        var address = '' + (hasher ? hasher.apply(this, arguments) : key);
        if (!_.has(cache, address)) cache[address] = func.apply(this, arguments);
        return cache[address];
        };
        memoize.cache = {};
        return memoize;
    };

```

-----------

4.

```js

    /** Used to compose bitmasks for cloning. */
    var CLONE_DEEP_FLAG = 1,
        CLONE_FLAT_FLAG = 2,
        CLONE_SYMBOLS_FLAG = 4;

```
> 注释

-----------

5.

```js

```
> 注释


