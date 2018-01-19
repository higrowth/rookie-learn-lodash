* <a href="#_camelcasestring">`_.camelCase`</a>
* <a href="#_capitalizestring">`_.capitalize`</a>
* <a href="#_deburrstring">`_.deburr`</a>
* <a href="#_endswithstring-target-positionstringlength">`_.endsWith`</a>
* <a href="#_escapestring">`_.escape`</a>
* <a href="#_escaperegexpstring">`_.escapeRegExp`</a>
* <a href="#_kebabcasestring">`_.kebabCase`</a>
* <a href="#_lowercasestring">`_.lowerCase`</a>
* <a href="#_lowerfirststring">`_.lowerFirst`</a>
* <a href="#_padstring-length0-chars">`_.pad`</a>
* <a href="#_padendstring-length0-chars">`_.padEnd`</a>
* <a href="#_padstartstring-length0-chars">`_.padStart`</a>
* <a href="#_parseintstring-radix10">`_.parseInt`</a>
* <a href="#_repeatstring-n1">`_.repeat`</a>
* <a href="#_replacestring-pattern-replacement">`_.replace`</a>
* <a href="#_snakecasestring">`_.snakeCase`</a>
* <a href="#_splitstring-separator-limit">`_.split`</a>
* <a href="#_startcasestring">`_.startCase`</a>
* <a href="#_startswithstring-target-position0">`_.startsWith`</a>
* <a href="#_templatestring-options">`_.template`</a>
* <a href="#_tolowerstring">`_.toLower`</a>
* <a href="#_toupperstring">`_.toUpper`</a>
* <a href="#_trimstring-charswhitespace">`_.trim`</a>
* <a href="#_trimendstring-charswhitespace">`_.trimEnd`</a>
* <a href="#_trimstartstring-charswhitespace">`_.trimStart`</a>
* <a href="#_truncatestring-options">`_.truncate`</a>
* <a href="#_unescapestring">`_.unescape`</a>
* <a href="#_uppercasestring">`_.upperCase`</a>
* <a href="#_upperfirststring">`_.upperFirst`</a>
* <a href="#_wordsstring-pattern">`_.words`</a>

## `“String” Methods`

<!-- div -->

<h3 id="_camelcasestring"><code>_.camelCase([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14117 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.camelcase "See the npm package") [&#x24C9;][1]

Converts `string` to [camel case](https://en.wikipedia.org/wiki/CamelCase).

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the camel cased string.

#### Example
```js
_.camelCase('Foo Bar');
// => 'fooBar'

_.camelCase('--foo-bar--');
// => 'fooBar'

_.camelCase('__FOO_BAR__');
// => 'fooBar'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_capitalizestring"><code>_.capitalize([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14137 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.capitalize "See the npm package") [&#x24C9;][1]

Converts the first character of `string` to upper case and the remaining
to lower case.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to capitalize.

#### Returns
*(string)*: Returns the capitalized string.

#### Example
```js
_.capitalize('FRED');
// => 'Fred'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_deburrstring"><code>_.deburr([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14159 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.deburr "See the npm package") [&#x24C9;][1]

Deburrs `string` by converting
[Latin-1 Supplement](https://en.wikipedia.org/wiki/Latin-1_Supplement_(Unicode_block)#Character_table)
and [Latin Extended-A](https://en.wikipedia.org/wiki/Latin_Extended-A)
letters to basic Latin letters and removing
[combining diacritical marks](https://en.wikipedia.org/wiki/Combining_Diacritical_Marks).

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to deburr.

#### Returns
*(string)*: Returns the deburred string.

#### Example
```js
_.deburr('déjà vu');
// => 'deja vu'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_endswithstring-target-positionstringlength"><code>_.endsWith([string=''], [target], [position=string.length])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14187 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.endswith "See the npm package") [&#x24C9;][1]

Checks if `string` ends with the given target string.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to inspect.
2. `[target]` *(string)*: The string to search for.
3. `[position=string.length]` *(number)*: The position to search up to.

#### Returns
*(boolean)*: Returns `true` if `string` ends with `target`, else `false`.

#### Example
```js
_.endsWith('abc', 'c');
// => true

_.endsWith('abc', 'b');
// => false

_.endsWith('abc', 'b', 2);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_escapestring"><code>_.escape([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14229 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.escape "See the npm package") [&#x24C9;][1]

Converts the characters "&", "<", ">", '"', and "'" in `string` to their
corresponding HTML entities.
<br>
<br>
**Note:** No other characters are escaped. To escape additional
characters use a third-party library like [_he_](https://mths.be/he).
<br>
<br>
Though the ">" character is escaped for symmetry, characters like
">" and "/" don't need escaping in HTML and have no special meaning
unless they're part of a tag or unquoted attribute value. See
[Mathias Bynens's article](https://mathiasbynens.be/notes/ambiguous-ampersands)
*(under "semi-related fun fact")* for more details.
<br>
<br>
When working with HTML you should always
[quote attribute values](http://wonko.com/post/html-escaping) to reduce
XSS vectors.

#### Since
0.1.0

#### Arguments
1. `[string='']` *(string)*: The string to escape.

#### Returns
*(string)*: Returns the escaped string.

#### Example
```js
_.escape('fred, barney, & pebbles');
// => 'fred, barney, &amp; pebbles'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_escaperegexpstring"><code>_.escapeRegExp([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14251 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.escaperegexp "See the npm package") [&#x24C9;][1]

Escapes the `RegExp` special characters "^", "$", "\", ".", "*", "+",
"?", "(", ")", "[", "]", "{", "}", and "|" in `string`.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to escape.

#### Returns
*(string)*: Returns the escaped string.

#### Example
```js
_.escapeRegExp('[lodash](https://lodash.com/)');
// => '\[lodash\]\(https://lodash\.com/\)'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_kebabcasestring"><code>_.kebabCase([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14279 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.kebabcase "See the npm package") [&#x24C9;][1]

Converts `string` to
[kebab case](https://en.wikipedia.org/wiki/Letter_case#Special_case_styles).

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the kebab cased string.

#### Example
```js
_.kebabCase('Foo Bar');
// => 'foo-bar'

_.kebabCase('fooBar');
// => 'foo-bar'

_.kebabCase('__FOO_BAR__');
// => 'foo-bar'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_lowercasestring"><code>_.lowerCase([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14303 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.lowercase "See the npm package") [&#x24C9;][1]

Converts `string`, as space separated words, to lower case.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the lower cased string.

#### Example
```js
_.lowerCase('--Foo-Bar--');
// => 'foo bar'

_.lowerCase('fooBar');
// => 'foo bar'

_.lowerCase('__FOO_BAR__');
// => 'foo bar'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_lowerfirststring"><code>_.lowerFirst([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14324 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.lowerfirst "See the npm package") [&#x24C9;][1]

Converts the first character of `string` to lower case.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the converted string.

#### Example
```js
_.lowerFirst('Fred');
// => 'fred'

_.lowerFirst('FRED');
// => 'fRED'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_padstring-length0-chars"><code>_.pad([string=''], [length=0], [chars=' '])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14349 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.pad "See the npm package") [&#x24C9;][1]

Pads `string` on the left and right sides if it's shorter than `length`.
Padding characters are truncated if they can't be evenly divided by `length`.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to pad.
2. `[length=0]` *(number)*: The padding length.
3. `[chars=' ']` *(string)*: The string used as padding.

#### Returns
*(string)*: Returns the padded string.

#### Example
```js
_.pad('abc', 8);
// => '  abc   '

_.pad('abc', 8, '_-');
// => '_-abc_-_'

_.pad('abc', 3);
// => 'abc'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_padendstring-length0-chars"><code>_.padEnd([string=''], [length=0], [chars=' '])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14388 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.padend "See the npm package") [&#x24C9;][1]

Pads `string` on the right side if it's shorter than `length`. Padding
characters are truncated if they exceed `length`.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to pad.
2. `[length=0]` *(number)*: The padding length.
3. `[chars=' ']` *(string)*: The string used as padding.

#### Returns
*(string)*: Returns the padded string.

#### Example
```js
_.padEnd('abc', 6);
// => 'abc   '

_.padEnd('abc', 6, '_-');
// => 'abc_-_'

_.padEnd('abc', 3);
// => 'abc'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_padstartstring-length0-chars"><code>_.padStart([string=''], [length=0], [chars=' '])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14421 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.padstart "See the npm package") [&#x24C9;][1]

Pads `string` on the left side if it's shorter than `length`. Padding
characters are truncated if they exceed `length`.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to pad.
2. `[length=0]` *(number)*: The padding length.
3. `[chars=' ']` *(string)*: The string used as padding.

#### Returns
*(string)*: Returns the padded string.

#### Example
```js
_.padStart('abc', 6);
// => '   abc'

_.padStart('abc', 6, '_-');
// => '_-_abc'

_.padStart('abc', 3);
// => 'abc'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_parseintstring-radix10"><code>_.parseInt(string, [radix=10])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14455 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.parseint "See the npm package") [&#x24C9;][1]

Converts `string` to an integer of the specified radix. If `radix` is
`undefined` or `0`, a `radix` of `10` is used unless `value` is a
hexadecimal, in which case a `radix` of `16` is used.
<br>
<br>
**Note:** This method aligns with the
[ES5 implementation](https://es5.github.io/#x15.1.2.2) of `parseInt`.

#### Since
1.1.0

#### Arguments
1. `string` *(string)*: The string to convert.
2. `[radix=10]` *(number)*: The radix to interpret `value` by.

#### Returns
*(number)*: Returns the converted integer.

#### Example
```js
_.parseInt('08');
// => 8

_.map(['6', '08', '10'], _.parseInt);
// => [6, 8, 10]
```
---

<!-- /div -->

<!-- div -->

<h3 id="_repeatstring-n1"><code>_.repeat([string=''], [n=1])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14486 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.repeat "See the npm package") [&#x24C9;][1]

Repeats the given string `n` times.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to repeat.
2. `[n=1]` *(number)*: The number of times to repeat the string.

#### Returns
*(string)*: Returns the repeated string.

#### Example
```js
_.repeat('*', 3);
// => '***'

_.repeat('abc', 2);
// => 'abcabc'

_.repeat('abc', 0);
// => ''
```
---

<!-- /div -->

<!-- div -->

<h3 id="_replacestring-pattern-replacement"><code>_.replace([string=''], pattern, replacement)</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14514 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.replace "See the npm package") [&#x24C9;][1]

Replaces matches for `pattern` in `string` with `replacement`.
<br>
<br>
**Note:** This method is based on
[`String#replace`](https://mdn.io/String/replace).

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to modify.
2. `pattern` *(RegExp|string)*: The pattern to replace.
3. `replacement` *(Function|string)*: The match replacement.

#### Returns
*(string)*: Returns the modified string.

#### Example
```js
_.replace('Hi Fred', 'Fred', 'Barney');
// => 'Hi Barney'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_snakecasestring"><code>_.snakeCase([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14542 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.snakecase "See the npm package") [&#x24C9;][1]

Converts `string` to
[snake case](https://en.wikipedia.org/wiki/Snake_case).

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the snake cased string.

#### Example
```js
_.snakeCase('Foo Bar');
// => 'foo_bar'

_.snakeCase('fooBar');
// => 'foo_bar'

_.snakeCase('--FOO-BAR--');
// => 'foo_bar'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_splitstring-separator-limit"><code>_.split([string=''], separator, [limit])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14565 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.split "See the npm package") [&#x24C9;][1]

Splits `string` by `separator`.
<br>
<br>
**Note:** This method is based on
[`String#split`](https://mdn.io/String/split).

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to split.
2. `separator` *(RegExp|string)*: The separator pattern to split by.
3. `[limit]` *(number)*: The length to truncate results to.

#### Returns
*(Array)*: Returns the string segments.

#### Example
```js
_.split('a-b-c', '-', 2);
// => ['a', 'b']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_startcasestring"><code>_.startCase([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14607 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.startcase "See the npm package") [&#x24C9;][1]

Converts `string` to
[start case](https://en.wikipedia.org/wiki/Letter_case#Stylistic_or_specialised_usage).

#### Since
3.1.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the start cased string.

#### Example
```js
_.startCase('--foo-bar--');
// => 'Foo Bar'

_.startCase('fooBar');
// => 'Foo Bar'

_.startCase('__FOO_BAR__');
// => 'FOO BAR'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_startswithstring-target-position0"><code>_.startsWith([string=''], [target], [position=0])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14634 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.startswith "See the npm package") [&#x24C9;][1]

Checks if `string` starts with the given target string.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to inspect.
2. `[target]` *(string)*: The string to search for.
3. `[position=0]` *(number)*: The position to search from.

#### Returns
*(boolean)*: Returns `true` if `string` starts with `target`, else `false`.

#### Example
```js
_.startsWith('abc', 'a');
// => true

_.startsWith('abc', 'b');
// => false

_.startsWith('abc', 'b', 1);
// => true
```
---

<!-- /div -->

<!-- div -->

<h3 id="_templatestring-options"><code>_.template([string=''], [options={}])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14748 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.template "See the npm package") [&#x24C9;][1]

Creates a compiled template function that can interpolate data properties
in "interpolate" delimiters, HTML-escape interpolated data properties in
"escape" delimiters, and execute JavaScript in "evaluate" delimiters. Data
properties may be accessed as free variables in the template. If a setting
object is given, it takes precedence over `_.templateSettings` values.
<br>
<br>
**Note:** In the development build `_.template` utilizes
[sourceURLs](http://www.html5rocks.com/en/tutorials/developertools/sourcemaps/#toc-sourceurl)
for easier debugging.
<br>
<br>
For more information on precompiling templates see
[lodash's custom builds documentation](https://lodash.com/custom-builds).
<br>
<br>
For more information on Chrome extension sandboxes see
[Chrome's extensions documentation](https://developer.chrome.com/extensions/sandboxingEval).

#### Since
0.1.0

#### Arguments
1. `[string='']` *(string)*: The template string.
2. `[options={}]` *(Object)*: The options object.
3. `[options.escape=_.templateSettings.escape]` *(RegExp)*: The HTML "escape" delimiter.
4. `[options.evaluate=_.templateSettings.evaluate]` *(RegExp)*: The "evaluate" delimiter.
5. `[options.imports=_.templateSettings.imports]` *(Object)*: An object to import into the template as free variables.
6. `[options.interpolate=_.templateSettings.interpolate]` *(RegExp)*: The "interpolate" delimiter.
7. `[options.sourceURL='lodash.templateSources[n]']` *(string)*: The sourceURL of the compiled template.
8. `[options.variable='obj']` *(string)*: The data object variable name.

#### Returns
*(Function)*: Returns the compiled template function.

#### Example
```js
// Use the "interpolate" delimiter to create a compiled template.
var compiled = _.template('hello <%= user %>!');
compiled({ 'user': 'fred' });
// => 'hello fred!'

// Use the HTML "escape" delimiter to escape data property values.
var compiled = _.template('<b><%- value %></b>');
compiled({ 'value': '<script>' });
// => '<b>&lt;script&gt;</b>'

// Use the "evaluate" delimiter to execute JavaScript and generate HTML.
var compiled = _.template('<% _.forEach(users, function(user) { %><li><%- user %></li><% }); %>');
compiled({ 'users': ['fred', 'barney'] });
// => '<li>fred</li><li>barney</li>'

// Use the internal `print` function in "evaluate" delimiters.
var compiled = _.template('<% print("hello " + user); %>!');
compiled({ 'user': 'barney' });
// => 'hello barney!'

// Use the ES template literal delimiter as an "interpolate" delimiter.
// Disable support by replacing the "interpolate" delimiter.
var compiled = _.template('hello ${ user }!');
compiled({ 'user': 'pebbles' });
// => 'hello pebbles!'

// Use backslashes to treat delimiters as plain text.
var compiled = _.template('<%= "\\<%- value %\\>" %>');
compiled({ 'value': 'ignored' });
// => '<%- value %>'

// Use the `imports` option to import `jQuery` as `jq`.
var text = '<% jq.each(users, function(user) { %><li><%- user %></li><% }); %>';
var compiled = _.template(text, { 'imports': { 'jq': jQuery } });
compiled({ 'users': ['fred', 'barney'] });
// => '<li>fred</li><li>barney</li>'

// Use the `sourceURL` option to specify a custom sourceURL for the template.
var compiled = _.template('hello <%= user %>!', { 'sourceURL': '/basic/greeting.jst' });
compiled(data);
// => Find the source of "greeting.jst" under the Sources tab or Resources panel of the web inspector.

// Use the `variable` option to ensure a with-statement isn't used in the compiled template.
var compiled = _.template('hi <%= data.user %>!', { 'variable': 'data' });
compiled.source;
// => function(data) {
//   var __t, __p = '';
//   __p += 'hi ' + ((__t = ( data.user )) == null ? '' : __t) + '!';
//   return __p;
// }

// Use custom template delimiters.
_.templateSettings.interpolate = /{{([\s\S]+?)}}/g;
var compiled = _.template('hello {{ user }}!');
compiled({ 'user': 'mustache' });
// => 'hello mustache!'

// Use the `source` property to inline compiled templates for meaningful
// line numbers in error messages and stack traces.
fs.writeFileSync(path.join(process.cwd(), 'jst.js'), '\
  var JST = {\
    "main": ' + _.template(mainText).source + '\
  };\
');
```
---

<!-- /div -->

<!-- div -->

<h3 id="_tolowerstring"><code>_.toLower([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14877 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.tolower "See the npm package") [&#x24C9;][1]

Converts `string`, as a whole, to lower case just like
[String#toLowerCase](https://mdn.io/toLowerCase).

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the lower cased string.

#### Example
```js
_.toLower('--Foo-Bar--');
// => '--foo-bar--'

_.toLower('fooBar');
// => 'foobar'

_.toLower('__FOO_BAR__');
// => '__foo_bar__'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_toupperstring"><code>_.toUpper([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14902 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.toupper "See the npm package") [&#x24C9;][1]

Converts `string`, as a whole, to upper case just like
[String#toUpperCase](https://mdn.io/toUpperCase).

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the upper cased string.

#### Example
```js
_.toUpper('--foo-bar--');
// => '--FOO-BAR--'

_.toUpper('fooBar');
// => 'FOOBAR'

_.toUpper('__foo_bar__');
// => '__FOO_BAR__'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_trimstring-charswhitespace"><code>_.trim([string=''], [chars=whitespace])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14928 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.trim "See the npm package") [&#x24C9;][1]

Removes leading and trailing whitespace or specified characters from `string`.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to trim.
2. `[chars=whitespace]` *(string)*: The characters to trim.

#### Returns
*(string)*: Returns the trimmed string.

#### Example
```js
_.trim('  abc  ');
// => 'abc'

_.trim('-_-abc-_-', '_-');
// => 'abc'

_.map(['  foo  ', '  bar  '], _.trim);
// => ['foo', 'bar']
```
---

<!-- /div -->

<!-- div -->

<h3 id="_trimendstring-charswhitespace"><code>_.trimEnd([string=''], [chars=whitespace])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14963 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.trimend "See the npm package") [&#x24C9;][1]

Removes trailing whitespace or specified characters from `string`.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to trim.
2. `[chars=whitespace]` *(string)*: The characters to trim.

#### Returns
*(string)*: Returns the trimmed string.

#### Example
```js
_.trimEnd('  abc  ');
// => '  abc'

_.trimEnd('-_-abc-_-', '_-');
// => '-_-abc'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_trimstartstring-charswhitespace"><code>_.trimStart([string=''], [chars=whitespace])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L14996 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.trimstart "See the npm package") [&#x24C9;][1]

Removes leading whitespace or specified characters from `string`.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to trim.
2. `[chars=whitespace]` *(string)*: The characters to trim.

#### Returns
*(string)*: Returns the trimmed string.

#### Example
```js
_.trimStart('  abc  ');
// => 'abc  '

_.trimStart('-_-abc-_-', '_-');
// => 'abc-_-'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_truncatestring-options"><code>_.truncate([string=''], [options={}])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15047 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.truncate "See the npm package") [&#x24C9;][1]

Truncates `string` if it's longer than the given maximum string length.
The last characters of the truncated string are replaced with the omission
string which defaults to "...".

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to truncate.
2. `[options={}]` *(Object)*: The options object.
3. `[options.length=30]` *(number)*: The maximum string length.
4. `[options.omission='...']` *(string)*: The string to indicate text is omitted.
5. `[options.separator]` *(RegExp|string)*: The separator pattern to truncate to.

#### Returns
*(string)*: Returns the truncated string.

#### Example
```js
_.truncate('hi-diddly-ho there, neighborino');
// => 'hi-diddly-ho there, neighbo...'

_.truncate('hi-diddly-ho there, neighborino', {
  'length': 24,
  'separator': ' '
});
// => 'hi-diddly-ho there,...'

_.truncate('hi-diddly-ho there, neighborino', {
  'length': 24,
  'separator': /,? +/
});
// => 'hi-diddly-ho there...'

_.truncate('hi-diddly-ho there, neighborino', {
  'omission': ' [...]'
});
// => 'hi-diddly-ho there, neig [...]'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_unescapestring"><code>_.unescape([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15122 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.unescape "See the npm package") [&#x24C9;][1]

The inverse of `_.escape`; this method converts the HTML entities
`&amp;`, `&lt;`, `&gt;`, `&quot;`, and `&#39;` in `string` to
their corresponding characters.
<br>
<br>
**Note:** No other HTML entities are unescaped. To unescape additional
HTML entities use a third-party library like [_he_](https://mths.be/he).

#### Since
0.6.0

#### Arguments
1. `[string='']` *(string)*: The string to unescape.

#### Returns
*(string)*: Returns the unescaped string.

#### Example
```js
_.unescape('fred, barney, &amp; pebbles');
// => 'fred, barney, & pebbles'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_uppercasestring"><code>_.upperCase([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15149 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.uppercase "See the npm package") [&#x24C9;][1]

Converts `string`, as space separated words, to upper case.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the upper cased string.

#### Example
```js
_.upperCase('--foo-bar');
// => 'FOO BAR'

_.upperCase('fooBar');
// => 'FOO BAR'

_.upperCase('__foo_bar__');
// => 'FOO BAR'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_upperfirststring"><code>_.upperFirst([string=''])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15170 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.upperfirst "See the npm package") [&#x24C9;][1]

Converts the first character of `string` to upper case.

#### Since
4.0.0

#### Arguments
1. `[string='']` *(string)*: The string to convert.

#### Returns
*(string)*: Returns the converted string.

#### Example
```js
_.upperFirst('fred');
// => 'Fred'

_.upperFirst('FRED');
// => 'FRED'
```
---

<!-- /div -->

<!-- div -->

<h3 id="_wordsstring-pattern"><code>_.words([string=''], [pattern])</code></h3>
[&#x24C8;](https://github.com/lodash/lodash/blob/4.17.4/lodash.js#L15191 "View in source") [&#x24C3;](https://www.npmjs.com/package/lodash.words "See the npm package") [&#x24C9;][1]

Splits `string` into an array of its words.

#### Since
3.0.0

#### Arguments
1. `[string='']` *(string)*: The string to inspect.
2. `[pattern]` *(RegExp|string)*: The pattern to match words.

#### Returns
*(Array)*: Returns the words of `string`.

#### Example
```js
_.words('fred, barney, & pebbles');
// => ['fred', 'barney', 'pebbles']

_.words('fred, barney, & pebbles', /[^, ]+/g);
// => ['fred', 'barney', '&', 'pebbles']
```
---

<!-- /div -->

<!-- /div -->

<!-- div -->

