# Tool工具函数


Table of Contents
----------------------

-   <a href="#isObject">isObject</a>
-   <a href="#isArrayLike">isLength</a>
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