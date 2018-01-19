# `“Date” Methods` (“日期”方法)

Table of Contents
----------------------

-   <a href="#_now">`_.now`</a>




<h2 id="_now">_.now()</h2>


#### 相关源码
```js
    /**
     * 获得 Unix 纪元(1970 1月1日 00:00:00 UTC) 直到现在的毫秒数
     *
     * @static
     * @memberOf _
     * @since 2.4.0
     * @category Date
     * @returns {number} 返回时间戳.
     * @example
     *
     * _.defer(function(stamp) {
     *   console.log(_.now() - stamp);
     * }, _.now());
     * // => Logs the number of milliseconds it took for the deferred invocation.
     */

    var now = ctxNow || function() {
        return root.Date.now();
    };

```
```js

    /** Detect free variable `global` from Node.js. */
    var freeGlobal = typeof global == 'object' && global && global.Object === Object && global;

    /** Detect free variable `self`. */
    var freeSelf = typeof self == 'object' && self && self.Object === Object && self;

    /** Used as a reference to the global object. */
    var root = freeGlobal || freeSelf || Function('return this')();

```
#### 注解
    由源码可以看出，_.now()方法直接返回的是Date对象中的now方法
    其中，源码可以看出root是当前运行环境下的全局对象。

-------



