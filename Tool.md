# Tool工具函数


Table of Contents
----------------------

-   <a href="#isObject">isObject</a>
-   <a href="#isIterateeCall">isIterateeCall</a>
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