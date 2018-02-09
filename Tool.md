# Tool工具函数


Table of Contents
----------------------

-   <a href="#addMapEntry">addMapEntry</a>
-   <a href="#addSetEntry">addSetEntry</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isArrayLike</a>
-   <a href="#isIterateeCall">isIterateeCall</a>



-----------------------

<h2 id="addMapEntry">addMapEntry</h2>

### 相关源码
```js

    /**
     * Adds the key-value `pair` to `map`.
     *
     * @private
     * @param {Object} map The map to modify.
     * @param {Array} pair The key-value pair to add.
     * @returns {Object} Returns `map`.
     */
    function addMapEntry(map, pair) {
      // Don't return `map.set` because it's not chainable in IE 11.
      map.set(pair[0], pair[1]);
      return map;
    }

```

### 注解

	往map中添加键值对，并返回map。

### 扩展

	Map 对象保存键值对。任何值(对象或者原始值) 都可以作为一个键或一个值。
	
	Objects 和 maps 的比较：
	Object 和 Map类似的一点是,它们都允许你按键存取一个值,都可以删除键,还可以检测一个键是否绑定了值.因此,一直以来,我们都把对象当成Map来使用,不过,现在有了Map,下面的区别解释了为什么使用Map更好点.
	1、一个对象通常都有自己的原型,所以一个对象总有一个"prototype"键。不过，从 ES5 开始可以使用 map = Object.create(null)来创建一个没有原型的对象。
	2、一个对象的键只能是字符串或者 Symbols，但一个 Map 的键可以是任意值。
	3、你可以通过size属性很容易地得到一个Map的键值对个数，而对象的键值对个数只能手动确认。

	注意：键的比较是基于 "SameValueZero" 算法：NaN 是与 NaN 相同的（虽然 NaN !== NaN），剩下所有其它的值是根据 === 运算符的结果判断是否相等。在目前的ECMAScript规范中，-0和+0被认为是相等的，尽管这在早期的草案中并不是这样。


-----------------------

<h2 id="addSetEntry">addSetEntry</h2>

### 相关源码
```js

	/**
	 * Adds `value` to `set`.
	 *
	 * @private
	 * @param {Object} set The set to modify.
	 * @param {*} value The value to add.
	 * @returns {Object} Returns `set`.
	 */
	function addSetEntry(set, value) {
		// Don't return `set.add` because it's not chainable in IE 11.
		set.add(value);
		return set;
	}

```

### 注解

	往集合中添加值，返回变更后的集合。

### 扩展 

	 Set对象是值的集合，你可以按照插入的顺序迭代它的元素。 Set中的元素只会出现一次，即 Set 中的元素是唯一的。

	 注意：因为 Set 中的值总是唯一的，所以需要判断两个值是否相等。在ECMAScript规范的早期版本中，这不是基于和===操作符中使用的算法相同的算法。具体来说，对于 Set s， +0 （+0 严格相等于-0）和-0是不同的值。然而，在 ECMAScript 2015规范中这点已被更改。另外，NaN和undefined都可以被存储在Set 中， NaN之间被视为相同的值（尽管 NaN !== NaN）。


-----------------------

<h2 id="isObject">isObject</h2>

### 相关源码
```js

	/**
     * 检测值是否是`Object`类型. (例如 arrays, functions, objects, regexes, `new Number(0)`, and `new String('')`)
     *
     * @static
     * @memberOf _
     * @since 0.1.0
     * @category Lang
     * @param {*} value 被检测的值.
     * @returns {boolean} 如果类型是`object`，则返回true，否则返回false.
     * @example
     *
     * _.isObject({});
     * // => true
     *
     * _.isObject([1, 2, 3]);
     * // => true
     *
     * _.isObject(_.noop);
     * // => true
     *
     * _.isObject(null);
     * // => false
     */
    function isObject(value) {
      var type = typeof value;
      return value != null && (type == 'object' || type == 'function');
    }

```

### 注解
    判断给定的值是否是object类型，此object类型不是单纯狭义上的`对象`，数组，函数，正则以及通过new关键字生成的String对象或Number对象等都是object类型

-----------------------

<h2 id="isLength">isLength</h2>

### 相关源码
```js

	/**
     * 检查“value”是否是一个有效的类似数组的长度.
     *
     * **Note:** This method is loosely based on
     * [`ToLength`](http://ecma-international.org/ecma-262/7.0/#sec-tolength).
     *
     * @static
     * @memberOf _
     * @since 4.0.0
     * @category Lang
     * @param {*} value 需要检测的值
     * @returns {boolean} Returns `true` if `value` is a valid length, else `false`.
     * @example
     *
     * _.isLength(3);
     * // => true
     *
     * _.isLength(Number.MIN_VALUE);
     * // => false
     *
     * _.isLength(Infinity);
     * // => false
     *
     * _.isLength('3');
     * // => false
     */
    function isLength(value) {
      return typeof value == 'number' &&
        value > -1 && value % 1 == 0 && value <= MAX_SAFE_INTEGER;
    }
	

```

### 注解
	判断给定的值是否是类似数组的长度，也就说，判断给定的参数是否是一个大于-1并且不大于 MAX_SAFE_INTEGER（最大安全整数）


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解


-----------------------


<h2 id="isArrayLike">isArrayLike</h2>

### 相关源码
```js

	/**
     * Checks if `value` is array-like. A value is considered array-like if it's
     * not a function and has a `value.length` that's an integer greater than or
     * equal to `0` and less than or equal to `Number.MAX_SAFE_INTEGER`.
     *
     * @static
     * @memberOf _
     * @since 4.0.0
     * @category Lang
     * @param {*} value The value to check.
     * @returns {boolean} Returns `true` if `value` is array-like, else `false`.
     * @example
     *
     * _.isArrayLike([1, 2, 3]);
     * // => true
     *
     * _.isArrayLike(document.body.children);
     * // => true
     *
     * _.isArrayLike('abc');
     * // => true
     *
     * _.isArrayLike(_.noop);
     * // => false
     */
    function isArrayLike(value) {
      return value != null && isLength(value.length) && !isFunction(value);
    }
	

```

### 注解


-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解



-----------------------

<h2 id=""></h2>

### 相关源码
```js

	

```

### 注解



-----------------------

<h2 id="isIterateeCall">isIterateeCall</h2>

### 相关源码
```js

	/**
     * 检查给定的参数是否来自迭代器调用.
     *
     * @private
     * @param {*} value The potential iteratee value argument.
     * @param {*} index The potential iteratee index or key argument.
     * @param {*} object The potential iteratee object argument.
     * @returns {boolean} Returns `true` if the arguments are from an iteratee call, else `false`.
     */
    function isIterateeCall(value, index, object) {
      if (!isObject(object)) {
        return false;
      }
      var type = typeof index;
      if (type == 'number'
            ? (isArrayLike(object) && isIndex(index, object.length))
            : (type == 'string' && index in object)
          ) {
        return eq(object[index], value);
      }
      return false;
    }

```

### 注解


--------------------