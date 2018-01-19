* <a href="#_aftern-func">`_.after`</a>
* <a href="#_aryfunc-nfunclength">`_.ary`</a>
* <a href="#_beforen-func">`_.before`</a>
* <a href="#_bindfunc-thisarg-partials">`_.bind`</a>
* <a href="#_bindkeyobject-key-partials">`_.bindKey`</a>
* <a href="#_curryfunc-arityfunclength">`_.curry`</a>
* <a href="#_curryrightfunc-arityfunclength">`_.curryRight`</a>
* <a href="#_debouncefunc-wait0-options">`_.debounce`</a>
* <a href="#_deferfunc-args">`_.defer`</a>
* <a href="#_delayfunc-wait-args">`_.delay`</a>
* <a href="#_flipfunc">`_.flip`</a>
* <a href="#_memoizefunc-resolver">`_.memoize`</a>
* <a href="#_negatepredicate">`_.negate`</a>
* <a href="#_oncefunc">`_.once`</a>
* <a href="#_overargsfunc-transforms_identity">`_.overArgs`</a>
* <a href="#_partialfunc-partials">`_.partial`</a>
* <a href="#_partialrightfunc-partials">`_.partialRight`</a>
* <a href="#_reargfunc-indexes">`_.rearg`</a>
* <a href="#_restfunc-startfunclength-1">`_.rest`</a>
* <a href="#_spreadfunc-start0">`_.spread`</a>
* <a href="#_throttlefunc-wait0-options">`_.throttle`</a>
* <a href="#_unaryfunc">`_.unary`</a>
* <a href="#_wrapvalue-wrapperidentity">`_.wrap`</a>


## `“Function” Methods`

<!-- div -->

<h3 id="_aftern-func"><code>_.after(n, func)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10007 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.after "See the npm package") [&#x24C9;][1]

The opposite of `_.before`; this method creates a function that invokes
`func` once it's called `n` or more times.

#### Since
0.1.0

#### Arguments
1. `n` *(number)*: The number of calls before `func` is invoked.
2. `func` *(Function)*: The function to restrict.

#### Returns
*(Function)*: Returns the new restricted function.

#### Example
```js
var saves = ['profile', 'settings'];

var done = _.after(saves.length, function() {
  console.log('done saving!');
});

_.forEach(saves, function(type) {
  asyncSave({ 'type': type, 'complete': done });
});
// => Logs 'done saving!' after the two async saves have completed.
```
---

<!-- /div -->

<!-- div -->

<h3 id="_aryfunc-nfunclength"><code>_.ary(func, [n=func.length])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10036 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.ary "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func`, with up to `n` arguments,
ignoring any additional arguments.

#### Since
3.0.0

#### Arguments
1. `func` *(Function)*: The function to cap arguments for.
2. `[n=func.length]` *(number)*: The arity cap.

#### Returns
*(Function)*: Returns the new capped function.

#### Example
```js
_.map(['6', '8', '10'], _.ary(parseInt, 1));
// => [6, 8, 10]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_beforen-func"><code>_.before(n, func)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10059 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.before "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func`, with the `this` binding and arguments
of the created function, while it's called less than `n` times. Subsequent
calls to the created function return the result of the last `func` invocation.

#### Since
3.0.0

#### Arguments
1. `n` *(number)*: The number of calls at which `func` is no longer invoked.
2. `func` *(Function)*: The function to restrict.

#### Returns
*(Function)*: Returns the new restricted function.

#### Example
```js
jQuery(element).on('click', _.before(5, addContactToList));
// => Allows adding up to 4 contacts to the list.
```
---

<!-- /div -->

<!-- div -->

<h3 id="_bindfunc-thisarg-partials"><code>_.bind(func, thisArg, [partials])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10111 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.bind "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with the `this` binding of `thisArg`
and `partials` prepended to the arguments it receives.
<br>
<br>
The `_.bind.placeholder` value, which defaults to `_` in monolithic builds,
may be used as a placeholder for partially applied arguments.
<br>
<br>
**Note:** Unlike native `Function#bind`, this method doesn't set the "length"
property of bound functions.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to bind.
2. `thisArg` *(&#42;)*: The `this` binding of `func`.
3. `[partials]` *(...&#42;)*: The arguments to be partially applied.

#### Returns
*(Function)*: Returns the new bound function.

#### Example
```js
function greet(greeting, punctuation) {
  return greeting + ' ' + this.user + punctuation;
}

var object = { 'user': 'fred' };

var bound = _.bind(greet, object, 'hi');
bound('!');
// => 'hi fred!'

// Bound with placeholders.
var bound = _.bind(greet, object, _, '!');
bound('hi');
// => 'hi fred!'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_bindkeyobject-key-partials"><code>_.bindKey(object, key, [partials])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10165 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.bindkey "See the npm package") [&#x24C9;][1]

Creates a function that invokes the method at `object[key]` with `partials`
prepended to the arguments it receives.
<br>
<br>
This method differs from `_.bind` by allowing bound functions to reference
methods that may be redefined or don't yet exist. See
[Peter Michaux's article](http://peter.michaux.ca/articles/lazy-function-definition-pattern)
for more details.
<br>
<br>
The `_.bindKey.placeholder` value, which defaults to `_` in monolithic
builds, may be used as a placeholder for partially applied arguments.

#### Since
0.10.0

#### Arguments
1. `object` *(Object)*: The object to invoke the method on.
2. `key` *(string)*: The key of the method.
3. `[partials]` *(...&#42;)*: The arguments to be partially applied.

#### Returns
*(Function)*: Returns the new bound function.

#### Example
```js
var object = {
  'user': 'fred',
  'greet': function(greeting, punctuation) {
    return greeting + ' ' + this.user + punctuation;
  }
};

var bound = _.bindKey(object, 'greet', 'hi');
bound('!');
// => 'hi fred!'

object.greet = function(greeting, punctuation) {
  return greeting + 'ya ' + this.user + punctuation;
};

bound('!');
// => 'hiya fred!'

// Bound with placeholders.
var bound = _.bindKey(object, 'greet', _, '!');
bound('hi');
// => 'hiya fred!'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_curryfunc-arityfunclength"><code>_.curry(func, [arity=func.length])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10215 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.curry "See the npm package") [&#x24C9;][1]

Creates a function that accepts arguments of `func` and either invokes
`func` returning its result, if at least `arity` number of arguments have
been provided, or returns a function that accepts the remaining `func`
arguments, and so on. The arity of `func` may be specified if `func.length`
is not sufficient.
<br>
<br>
The `_.curry.placeholder` value, which defaults to `_` in monolithic builds,
may be used as a placeholder for provided arguments.
<br>
<br>
**Note:** This method doesn't set the "length" property of curried functions.

#### Since
2.0.0

#### Arguments
1. `func` *(Function)*: The function to curry.
2. `[arity=func.length]` *(number)*: The arity of `func`.

#### Returns
*(Function)*: Returns the new curried function.

#### Example
```js
var abc = function(a, b, c) {
  return [a, b, c];
};

var curried = _.curry(abc);

curried(1)(2)(3);
// => [1, 2, 3]

curried(1, 2)(3);
// => [1, 2, 3]

curried(1, 2, 3);
// => [1, 2, 3]

// Curried with placeholders.
curried(1)(_, 3)(2);
// => [1, 2, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_curryrightfunc-arityfunclength"><code>_.curryRight(func, [arity=func.length])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10260 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.curryright "See the npm package") [&#x24C9;][1]

This method is like `_.curry` except that arguments are applied to `func`
in the manner of `_.partialRight` instead of `_.partial`.
<br>
<br>
The `_.curryRight.placeholder` value, which defaults to `_` in monolithic
builds, may be used as a placeholder for provided arguments.
<br>
<br>
**Note:** This method doesn't set the "length" property of curried functions.

#### Since
3.0.0

#### Arguments
1. `func` *(Function)*: The function to curry.
2. `[arity=func.length]` *(number)*: The arity of `func`.

#### Returns
*(Function)*: Returns the new curried function.

#### Example
```js
var abc = function(a, b, c) {
  return [a, b, c];
};

var curried = _.curryRight(abc);

curried(3)(2)(1);
// => [1, 2, 3]

curried(2, 3)(1);
// => [1, 2, 3]

curried(1, 2, 3);
// => [1, 2, 3]

// Curried with placeholders.
curried(3)(1, _)(2);
// => [1, 2, 3]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_debouncefunc-wait0-options"><code>_.debounce(func, [wait=0], [options={}])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10321 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.debounce "See the npm package") [&#x24C9;][1]

Creates a debounced function that delays invoking `func` until after `wait`
milliseconds have elapsed since the last time the debounced function was
invoked. The debounced function comes with a `cancel` method to cancel
delayed `func` invocations and a `flush` method to immediately invoke them.
Provide `options` to indicate whether `func` should be invoked on the
leading and/or trailing edge of the `wait` timeout. The `func` is invoked
with the last arguments provided to the debounced function. Subsequent
calls to the debounced function return the result of the last `func`
invocation.
<br>
<br>
**Note:** If `leading` and `trailing` options are `true`, `func` is
invoked on the trailing edge of the timeout only if the debounced function
is invoked more than once during the `wait` timeout.
<br>
<br>
If `wait` is `0` and `leading` is `false`, `func` invocation is deferred
until to the next tick, similar to `setTimeout` with a timeout of `0`.
<br>
<br>
See [David Corbacho's article](https://css-tricks.com/debouncing-throttling-explained-examples/)
for details over the differences between `_.debounce` and `_.throttle`.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to debounce.
2. `[wait=0]` *(number)*: The number of milliseconds to delay.
3. `[options={}]` *(Object)*: The options object.
4. `[options.leading=false]` *(boolean)*: Specify invoking on the leading edge of the timeout.
5. `[options.maxWait]` *(number)*: The maximum time `func` is allowed to be delayed before it's invoked.
6. `[options.trailing=true]` *(boolean)*: Specify invoking on the trailing edge of the timeout.

#### Returns
*(Function)*: Returns the new debounced function.

#### Example
```js
// Avoid costly calculations while the window size is in flux.
jQuery(window).on('resize', _.debounce(calculateLayout, 150));

// Invoke `sendMail` when clicked, debouncing subsequent calls.
jQuery(element).on('click', _.debounce(sendMail, 300, {
  'leading': true,
  'trailing': false
}));

// Ensure `batchLog` is invoked once after 1 second of debounced calls.
var debounced = _.debounce(batchLog, 250, { 'maxWait': 1000 });
var source = new EventSource('/stream');
jQuery(source).on('message', debounced);

// Cancel the trailing debounced invocation.
jQuery(window).on('popstate', debounced.cancel);
```
---

<!-- /div -->

<!-- div -->

<h3 id="_deferfunc-args"><code>_.defer(func, [args])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10461 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.defer "See the npm package") [&#x24C9;][1]

Defers invoking the `func` until the current call stack has cleared. Any
additional arguments are provided to `func` when it's invoked.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to defer.
2. `[args]` *(...&#42;)*: The arguments to invoke `func` with.

#### Returns
*(number)*: Returns the timer id.

#### Example
```js
_.defer(function(text) {
  console.log(text);
}, 'deferred');
// => Logs 'deferred' after one millisecond.
```
---

<!-- /div -->

<!-- div -->

<h3 id="_delayfunc-wait-args"><code>_.delay(func, wait, [args])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10484 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.delay "See the npm package") [&#x24C9;][1]

Invokes `func` after `wait` milliseconds. Any additional arguments are
provided to `func` when it's invoked.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to delay.
2. `wait` *(number)*: The number of milliseconds to delay invocation.
3. `[args]` *(...&#42;)*: The arguments to invoke `func` with.

#### Returns
*(number)*: Returns the timer id.

#### Example
```js
_.delay(function(text) {
  console.log(text);
}, 1000, 'later');
// => Logs 'later' after one second.
```
---

<!-- /div -->

<!-- div -->

<h3 id="_flipfunc"><code>_.flip(func)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10506 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.flip "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with arguments reversed.

#### Since
4.0.0

#### Arguments
1. `func` *(Function)*: The function to flip arguments for.

#### Returns
*(Function)*: Returns the new flipped function.

#### Example
```js
var flipped = _.flip(function() {
  return _.toArray(arguments);
});

flipped('a', 'b', 'c', 'd');
// => ['d', 'c', 'b', 'a']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_memoizefunc-resolver"><code>_.memoize(func, [resolver])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10554 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.memoize "See the npm package") [&#x24C9;][1]

Creates a function that memoizes the result of `func`. If `resolver` is
provided, it determines the cache key for storing the result based on the
arguments provided to the memoized function. By default, the first argument
provided to the memoized function is used as the map cache key. The `func`
is invoked with the `this` binding of the memoized function.
<br>
<br>
**Note:** The cache is exposed as the `cache` property on the memoized
function. Its creation may be customized by replacing the `_.memoize.Cache`
constructor with one whose instances implement the
[`Map`](http://ecma-international.org/ecma-262/7.0/#sec-properties-of-the-map-prototype-object)
method interface of `clear`, `delete`, `get`, `has`, and `set`.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to have its output memoized.
2. `[resolver]` *(Function)*: The function to resolve the cache key.

#### Returns
*(Function)*: Returns the new memoized function.

#### Example
```js
var object = { 'a': 1, 'b': 2 };
var other = { 'c': 3, 'd': 4 };

var values = _.memoize(_.values);
values(object);
// => [1, 2]

values(other);
// => [3, 4]

object.a = 2;
values(object);
// => [1, 2]

// Modify the result cache.
values.cache.set(object, ['a', 'b']);
values(object);
// => ['a', 'b']

// Replace `_.memoize.Cache`.
_.memoize.Cache = WeakMap;
```
---

<!-- /div -->

<!-- div -->

<h3 id="_negatepredicate"><code>_.negate(predicate)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10597 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.negate "See the npm package") [&#x24C9;][1]

Creates a function that negates the result of the predicate `func`. The
`func` predicate is invoked with the `this` binding and arguments of the
created function.

#### Since
3.0.0

#### Arguments
1. `predicate` *(Function)*: The predicate to negate.

#### Returns
*(Function)*: Returns the new negated function.

#### Example
```js
function isEven(n) {
  return n % 2 == 0;
}

_.filter([1, 2, 3, 4, 5, 6], _.negate(isEven));
// => [1, 3, 5]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_oncefunc"><code>_.once(func)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10631 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.once "See the npm package") [&#x24C9;][1]

Creates a function that is restricted to invoking `func` once. Repeat calls
to the function return the value of the first invocation. The `func` is
invoked with the `this` binding and arguments of the created function.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to restrict.

#### Returns
*(Function)*: Returns the new restricted function.

#### Example
```js
var initialize = _.once(createApplication);
initialize();
initialize();
// => `createApplication` is invoked once
```
---

<!-- /div -->

<!-- div -->

<h3 id="_overargsfunc-transforms_identity"><code>_.overArgs(func, [transforms=[_.identity]])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10666 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.overargs "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with its arguments transformed.

#### Since
4.0.0

#### Arguments
1. `func` *(Function)*: The function to wrap.
2. `[transforms=[_.identity]]` *(...(Function|Function&#91;&#93;))*: The argument transforms.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
function doubled(n) {
  return n * 2;
}

function square(n) {
  return n * n;
}

var func = _.overArgs(function(x, y) {
  return [x, y];
}, [square, doubled]);

func(9, 3);
// => [81, 6]

func(10, 5);
// => [100, 10]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_partialfunc-partials"><code>_.partial(func, [partials])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10716 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.partial "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with `partials` prepended to the
arguments it receives. This method is like `_.bind` except it does **not**
alter the `this` binding.
<br>
<br>
The `_.partial.placeholder` value, which defaults to `_` in monolithic
builds, may be used as a placeholder for partially applied arguments.
<br>
<br>
**Note:** This method doesn't set the "length" property of partially
applied functions.

#### Since
0.2.0

#### Arguments
1. `func` *(Function)*: The function to partially apply arguments to.
2. `[partials]` *(...&#42;)*: The arguments to be partially applied.

#### Returns
*(Function)*: Returns the new partially applied function.

#### Example
```js
function greet(greeting, name) {
  return greeting + ' ' + name;
}

var sayHelloTo = _.partial(greet, 'hello');
sayHelloTo('fred');
// => 'hello fred'

// Partially applied with placeholders.
var greetFred = _.partial(greet, _, 'fred');
greetFred('hi');
// => 'hi fred'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_partialrightfunc-partials"><code>_.partialRight(func, [partials])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10753 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.partialright "See the npm package") [&#x24C9;][1]

This method is like `_.partial` except that partially applied arguments
are appended to the arguments it receives.
<br>
<br>
The `_.partialRight.placeholder` value, which defaults to `_` in monolithic
builds, may be used as a placeholder for partially applied arguments.
<br>
<br>
**Note:** This method doesn't set the "length" property of partially
applied functions.

#### Since
1.0.0

#### Arguments
1. `func` *(Function)*: The function to partially apply arguments to.
2. `[partials]` *(...&#42;)*: The arguments to be partially applied.

#### Returns
*(Function)*: Returns the new partially applied function.

#### Example
```js
function greet(greeting, name) {
  return greeting + ' ' + name;
}

var greetFred = _.partialRight(greet, 'fred');
greetFred('hi');
// => 'hi fred'

// Partially applied with placeholders.
var sayHelloTo = _.partialRight(greet, 'hello', _);
sayHelloTo('fred');
// => 'hello fred'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_reargfunc-indexes"><code>_.rearg(func, indexes)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10780 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.rearg "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with arguments arranged according
to the specified `indexes` where the argument value at the first index is
provided as the first argument, the argument value at the second index is
provided as the second argument, and so on.

#### Since
3.0.0

#### Arguments
1. `func` *(Function)*: The function to rearrange arguments for.
2. `indexes` *(...(number|number&#91;&#93;))*: The arranged argument indexes.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var rearged = _.rearg(function(a, b, c) {
  return [a, b, c];
}, [2, 0, 1]);

rearged('b', 'c', 'a')
// => ['a', 'b', 'c']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_restfunc-startfunclength-1"><code>_.rest(func, [start=func.length-1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10809 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.rest "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with the `this` binding of the
created function and arguments from `start` and beyond provided as
an array.
<br>
<br>
**Note:** This method is based on the
[rest parameter](https://mdn.io/rest_parameters).

#### Since
4.0.0

#### Arguments
1. `func` *(Function)*: The function to apply a rest parameter to.
2. `[start=func.length-1]` *(number)*: The start position of the rest parameter.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var say = _.rest(function(what, names) {
  return what + ' ' + _.initial(names).join(', ') +
    (_.size(names) > 1 ? ', & ' : '') + _.last(names);
});

say('hello', 'fred', 'barney', 'pebbles');
// => 'hello fred, barney, & pebbles'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_spreadfunc-start0"><code>_.spread(func, [start=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10851 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.spread "See the npm package") [&#x24C9;][1]

Creates a function that invokes `func` with the `this` binding of the
create function and an array of arguments much like
[`Function#apply`](http://www.ecma-international.org/ecma-262/7.0/#sec-function.prototype.apply).
<br>
<br>
**Note:** This method is based on the
[spread operator](https://mdn.io/spread_operator).

#### Since
3.2.0

#### Arguments
1. `func` *(Function)*: The function to spread arguments over.
2. `[start=0]` *(number)*: The start position of the spread.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var say = _.spread(function(who, what) {
  return who + ' says ' + what;
});

say(['fred', 'hello']);
// => 'fred says hello'

var numbers = Promise.all([
  Promise.resolve(40),
  Promise.resolve(36)
]);

numbers.then(_.spread(function(x, y) {
  return x + y;
}));
// => a Promise of 76
```
---

<!-- /div -->

<!-- div -->

<h3 id="_throttlefunc-wait0-options"><code>_.throttle(func, [wait=0], [options={}])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10911 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.throttle "See the npm package") [&#x24C9;][1]

Creates a throttled function that only invokes `func` at most once per
every `wait` milliseconds. The throttled function comes with a `cancel`
method to cancel delayed `func` invocations and a `flush` method to
immediately invoke them. Provide `options` to indicate whether `func`
should be invoked on the leading and/or trailing edge of the `wait`
timeout. The `func` is invoked with the last arguments provided to the
throttled function. Subsequent calls to the throttled function return the
result of the last `func` invocation.
<br>
<br>
**Note:** If `leading` and `trailing` options are `true`, `func` is
invoked on the trailing edge of the timeout only if the throttled function
is invoked more than once during the `wait` timeout.
<br>
<br>
If `wait` is `0` and `leading` is `false`, `func` invocation is deferred
until to the next tick, similar to `setTimeout` with a timeout of `0`.
<br>
<br>
See [David Corbacho's article](https://css-tricks.com/debouncing-throttling-explained-examples/)
for details over the differences between `_.throttle` and `_.debounce`.

#### Since
0.1.0

#### Arguments
1. `func` *(Function)*: The function to throttle.
2. `[wait=0]` *(number)*: The number of milliseconds to throttle invocations to.
3. `[options={}]` *(Object)*: The options object.
4. `[options.leading=true]` *(boolean)*: Specify invoking on the leading edge of the timeout.
5. `[options.trailing=true]` *(boolean)*: Specify invoking on the trailing edge of the timeout.

#### Returns
*(Function)*: Returns the new throttled function.

#### Example
```js
// Avoid excessively updating the position while scrolling.
jQuery(window).on('scroll', _.throttle(updatePosition, 100));

// Invoke `renewToken` when the click event is fired, but not more than once every 5 minutes.
var throttled = _.throttle(renewToken, 300000, { 'trailing': false });
jQuery(element).on('click', throttled);

// Cancel the trailing throttled invocation.
jQuery(window).on('popstate', throttled.cancel);
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unaryfunc"><code>_.unary(func)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10944 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.unary "See the npm package") [&#x24C9;][1]

Creates a function that accepts up to one argument, ignoring any
additional arguments.

#### Since
4.0.0

#### Arguments
1. `func` *(Function)*: The function to cap arguments for.

#### Returns
*(Function)*: Returns the new capped function.

#### Example
```js
_.map(['6', '8', '10'], _.unary(parseInt));
// => [6, 8, 10]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_wrapvalue-wrapperidentity"><code>_.wrap(value, [wrapper=identity])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L10970 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.wrap "See the npm package") [&#x24C9;][1]

Creates a function that provides `value` to `wrapper` as its first
argument. Any additional arguments provided to the function are appended
to those provided to the `wrapper`. The wrapper is invoked with the `this`
binding of the created function.

#### Since
0.1.0

#### Arguments
1. `value` *(&#42;)*: The value to wrap.
2. `[wrapper=identity]` *(Function)*: The wrapper function.

#### Returns
*(Function)*: Returns the new function.

#### Example
```js
var p = _.wrap(_.escape, function(func, text) {
  return '<p>' + func(text) + '</p>';
});

p('fred, barney, & pebbles');
// => '<p>fred, barney, &amp; pebbles</p>'
```
---

<!-- /div -->

<!-- /div -->

<!-- div -->