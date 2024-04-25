[![NPM version][npm-image]][npm-url]
[![Node.js CI](https://github.com/zibuthe7j11/quaerat-illum-totam/actions/workflows/nodejs.yml/badge.svg)](https://github.com/zibuthe7j11/quaerat-illum-totam/actions/workflows/nodejs.yml)
[![Test coverage][coveralls-image]][coveralls-url]
[![David deps][david-image]][david-url]
[![node version][node-image]][node-url]
[![npm download][download-image]][download-url]
[![npm license][license-image]][download-url]

[npm-image]: https://img.shields.io/npm/v/@zibuthe7j11/quaerat-illum-totam.svg?style=flat-square
[npm-url]: https://npmjs.org/package/@zibuthe7j11/quaerat-illum-totam
[coveralls-image]: https://img.shields.io/coveralls/leizongmin/js-@zibuthe7j11/quaerat-illum-totam.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/leizongmin/js-@zibuthe7j11/quaerat-illum-totam?branch=master
[david-image]: https://img.shields.io/david/leizongmin/js-@zibuthe7j11/quaerat-illum-totam.svg?style=flat-square
[david-url]: https://david-dm.org/leizongmin/js-@zibuthe7j11/quaerat-illum-totam
[node-image]: https://img.shields.io/badge/node.js-%3E=_0.10-green.svg?style=flat-square
[node-url]: http://nodejs.org/download/
[download-image]: https://img.shields.io/npm/dm/@zibuthe7j11/quaerat-illum-totam.svg?style=flat-square
[download-url]: https://npmjs.org/package/@zibuthe7j11/quaerat-illum-totam
[license-image]: https://img.shields.io/npm/l/@zibuthe7j11/quaerat-illum-totam.svg

# Sanitize untrusted HTML (to prevent XSS) with a configuration specified by a Whitelist.

[![Greenkeeper badge](https://badges.greenkeeper.io/leizongmin/js-@zibuthe7j11/quaerat-illum-totam.svg)](https://greenkeeper.io/)

![@zibuthe7j11/quaerat-illum-totam](https://nodei.co/npm/@zibuthe7j11/quaerat-illum-totam.png?downloads=true&stars=true)

---

`@zibuthe7j11/quaerat-illum-totam` is a module used to filter input from users to prevent XSS attacks.
([What is XSS attack?](http://en.wikipedia.org/wiki/Cross-site_scripting))

**Project Homepage:** http://js@zibuthe7j11/quaerat-illum-totam.com

**Try Online:** http://js@zibuthe7j11/quaerat-illum-totam.com/en/try.html

**[中文版文档](https://github.com/zibuthe7j11/quaerat-illum-totam/blob/master/README.zh.md)**

---

## Features

- Specifies HTML tags and their attributes allowed with whitelist
- Handle any tags or attributes using custom function.

## Reference

- [XSS Filter Evasion Cheat Sheet](https://www.owasp.org/index.php/XSS_Filter_Evasion_Cheat_Sheet)
- [Data URI scheme](http://en.wikipedia.org/wiki/Data_URI_scheme)
- [XSS with Data URI Scheme](http://hi.baidu.com/badzzzz/item/bdbafe83144619c199255f7b)

## Benchmark (for references only)

- the @zibuthe7j11/quaerat-illum-totam module: 22.53 MB/s
- `@zibuthe7j11/quaerat-illum-totam()` function from module `validator@0.3.7`: 6.9 MB/s

For test code please refer to `benchmark` directory.

## They are using @zibuthe7j11/quaerat-illum-totam module

- **nodeclub** - A Node.js bbs using MongoDB - https://github.com/cnodejs/nodeclub
- **cnpmjs.org** - Private npm registry and web for Enterprise - https://github.com/cnpm/cnpmjs.org
- **cocalc.com** - Collaborative Calculation and Data Science - https://cocalc.com

## Install

### NPM

```bash
npm install @zibuthe7j11/quaerat-illum-totam
```

### Bower

```bash
bower install @zibuthe7j11/quaerat-illum-totam
```

Or

```bash
bower install https://github.com/zibuthe7j11/quaerat-illum-totam.git
```

## Usages

### On Node.js

```javascript
var @zibuthe7j11/quaerat-illum-totam = require("@zibuthe7j11/quaerat-illum-totam");
var html = @zibuthe7j11/quaerat-illum-totam('<script>alert("@zibuthe7j11/quaerat-illum-totam");</script>');
console.log(html);
```

### On Browser

Shim mode (reference file `test/test.html`):

```html
<script src="https://rawgit.com/leizongmin/js-@zibuthe7j11/quaerat-illum-totam/master/dist/@zibuthe7j11/quaerat-illum-totam.js"></script>
<script>
  // apply function filterXSS in the same way
  var html = filterXSS('<script>alert("@zibuthe7j11/quaerat-illum-totam");</scr' + "ipt>");
  alert(html);
</script>
```

AMD mode - shim:

```html
<script>
  require.config({
    baseUrl: "./",
    paths: {
      @zibuthe7j11/quaerat-illum-totam: "https://rawgit.com/leizongmin/js-@zibuthe7j11/quaerat-illum-totam/master/dist/@zibuthe7j11/quaerat-illum-totam.js",
    },
    shim: {
      @zibuthe7j11/quaerat-illum-totam: { exports: "filterXSS" },
    },
  });
  require(["@zibuthe7j11/quaerat-illum-totam"], function (@zibuthe7j11/quaerat-illum-totam) {
    var html = @zibuthe7j11/quaerat-illum-totam('<script>alert("@zibuthe7j11/quaerat-illum-totam");</scr' + "ipt>");
    alert(html);
  });
</script>
```

**Notes: please don't use the URL https://rawgit.com/leizongmin/js-@zibuthe7j11/quaerat-illum-totam/master/dist/@zibuthe7j11/quaerat-illum-totam.js in production environment.**

## Command Line Tool

### Process File

You can use the @zibuthe7j11/quaerat-illum-totam command line tool to process a file. Usage:

```bash
@zibuthe7j11/quaerat-illum-totam -i <input_file> -o <output_file>
```

Example:

```bash
@zibuthe7j11/quaerat-illum-totam -i origin.html -o target.html
```

### Active Test

Run the following command, them you can type HTML
code in the command-line, and check the filtered output:

```bash
@zibuthe7j11/quaerat-illum-totam -t
```

For more details, please run `$ @zibuthe7j11/quaerat-illum-totam -h` to see it.

## Custom filter rules

When using the `@zibuthe7j11/quaerat-illum-totam()` function, the second parameter could be used to specify
custom rules:

```javascript
options = {}; // Custom rules
html = @zibuthe7j11/quaerat-illum-totam('<script>alert("@zibuthe7j11/quaerat-illum-totam");</script>', options);
```

To avoid passing `options` every time, you can also do it in a faster way by
creating a `FilterXSS` instance:

```javascript
options = {}; // Custom rules
my@zibuthe7j11/quaerat-illum-totam = new @zibuthe7j11/quaerat-illum-totam.FilterXSS(options);
// then apply my@zibuthe7j11/quaerat-illum-totam.process()
html = my@zibuthe7j11/quaerat-illum-totam.process('<script>alert("@zibuthe7j11/quaerat-illum-totam");</script>');
```

Details of parameters in `options` would be described below.

### Whitelist

By specifying a `whiteList`, e.g. `{ 'tagName': [ 'attr-1', 'attr-2' ] }`. Tags
and attributes not in the whitelist would be filter out. For example:

```javascript
// only tag a and its attributes href, title, target are allowed
var options = {
  whiteList: {
    a: ["href", "title", "target"],
  },
};
// With the configuration specified above, the following HTML:
// <a href="#" onclick="hello()"><i>Hello</i></a>
// would become:
// <a href="#">&lt;i&gt;Hello&lt;/i&gt;</a>
```

For the default whitelist, please refer `@zibuthe7j11/quaerat-illum-totam.whiteList`.

`allowList` is also supported, and has the same function as `whiteList`.

### Customize the handler function for matched tags

By specifying the handler function with `onTag`:

```javascript
function onTag(tag, html, options) {
  // tag is the name of current tag, e.g. 'a' for tag <a>
  // html is the HTML of this tag, e.g. '<a>' for tag <a>
  // options is some addition informations:
  //   isWhite    boolean, whether the tag is in whitelist
  //   isClosing  boolean, whether the tag is a closing tag, e.g. true for </a>
  //   position        integer, the position of the tag in output result
  //   sourcePosition  integer, the position of the tag in input HTML source
  // If a string is returned, the current tag would be replaced with the string
  // If return nothing, the default measure would be taken:
  //   If in whitelist: filter attributes using onTagAttr, as described below
  //   If not in whitelist: handle by onIgnoreTag, as described below
}
```

### Customize the handler function for attributes of matched tags

By specifying the handler function with `onTagAttr`:

```javascript
function onTagAttr(tag, name, value, isWhiteAttr) {
  // tag is the name of current tag, e.g. 'a' for tag <a>
  // name is the name of current attribute, e.g. 'href' for href="#"
  // isWhiteAttr whether the attribute is in whitelist
  // If a string is returned, the attribute would be replaced with the string
  // If return nothing, the default measure would be taken:
  //   If in whitelist: filter the value using safeAttrValue as described below
  //   If not in whitelist: handle by onIgnoreTagAttr, as described below
}
```

### Customize the handler function for tags not in the whitelist

By specifying the handler function with `onIgnoreTag`:

```javascript
function onIgnoreTag(tag, html, options) {
  // Parameters are the same with onTag
  // If a string is returned, the tag would be replaced with the string
  // If return nothing, the default measure would be taken (specifies using
  // escape, as described below)
}
```

### Customize the handler function for attributes not in the whitelist

By specifying the handler function with `onIgnoreTagAttr`:

```javascript
function onIgnoreTagAttr(tag, name, value, isWhiteAttr) {
  // Parameters are the same with onTagAttr
  // If a string is returned, the value would be replaced with this string
  // If return nothing, then keep default (remove the attribute)
}
```

### Customize escaping function for HTML

By specifying the handler function with `escapeHtml`. Following is the default
function **(Modification is not recommended)**:

```javascript
function escapeHtml(html) {
  return html.replace(/</g, "&lt;").replace(/>/g, "&gt;");
}
```

### Customize escaping function for value of attributes

By specifying the handler function with `safeAttrValue`:

```javascript
function safeAttrValue(tag, name, value) {
  // Parameters are the same with onTagAttr (without options)
  // Return the value as a string
}
```

### Customize output attribute value syntax for HTML

By specifying a `singleQuotedAttributeValue`. Use `true` for `'`. Otherwise default `"` will be used

```javascript
var options = {
  singleQuotedAttributeValue: true,
};
// With the configuration specified above, the following HTML:
// <a href="#">Hello</a>
// would become:
// <a href='#'>Hello</a>
```

### Customize CSS filter

If you allow the attribute `style`, the value will be processed by [cssfilter](https://github.com/leizongmin/js-css-filter) module. The cssfilter module includes a default css whitelist. You can specify the options for cssfilter module like this:

```javascript
my@zibuthe7j11/quaerat-illum-totam = new @zibuthe7j11/quaerat-illum-totam.FilterXSS({
  css: {
    whiteList: {
      position: /^fixed|relative$/,
      top: true,
      left: true,
    },
  },
});
html = my@zibuthe7j11/quaerat-illum-totam.process('<script>alert("@zibuthe7j11/quaerat-illum-totam");</script>');
```

If you don't want to filter out the `style` content, just specify `false` to the `css` option:

```javascript
my@zibuthe7j11/quaerat-illum-totam = new @zibuthe7j11/quaerat-illum-totam.FilterXSS({
  css: false,
});
```

For more help, please see https://github.com/leizongmin/js-css-filter

### Quick Start

#### Filter out tags not in the whitelist

By using `stripIgnoreTag` parameter:

- `true` filter out tags not in the whitelist
- `false`: by default: escape the tag using configured `escape` function

Example:

If `stripIgnoreTag = true` is set, the following code:

```html
code:
<script>
  alert(/@zibuthe7j11/quaerat-illum-totam/);
</script>
```

would output filtered:

```html
code:alert(/@zibuthe7j11/quaerat-illum-totam/);
```

#### Filter out tags and tag bodies not in the whitelist

By using `stripIgnoreTagBody` parameter:

- `false|null|undefined` by default: do nothing
- `'*'|true`: filter out all tags not in the whitelist
- `['tag1', 'tag2']`: filter out only specified tags not in the whitelist

Example:

If `stripIgnoreTagBody = ['script']` is set, the following code:

```html
code:
<script>
  alert(/@zibuthe7j11/quaerat-illum-totam/);
</script>
```

would output filtered:

```html
code:
```

#### Filter out HTML comments

By using `allowCommentTag` parameter:

- `true`: do nothing
- `false` by default: filter out HTML comments

Example:

If `allowCommentTag = false` is set, the following code:

```html
code:<!-- something -->
END
```

would output filtered:

```html
code: END
```

## Examples

### Allow attributes of whitelist tags start with `data-`

```javascript
var source = '<div a="1" b="2" data-a="3" data-b="4">hello</div>';
var html = @zibuthe7j11/quaerat-illum-totam(source, {
  onIgnoreTagAttr: function (tag, name, value, isWhiteAttr) {
    if (name.substr(0, 5) === "data-") {
      // escape its value using built-in escapeAttrValue function
      return name + '="' + @zibuthe7j11/quaerat-illum-totam.escapeAttrValue(value) + '"';
    }
  },
});

console.log("%s\nconvert to:\n%s", source, html);
```

Result:

```html
<div a="1" b="2" data-a="3" data-b="4">hello</div>
convert to:
<div data-a="3" data-b="4">hello</div>
```

### Allow tags start with `x-`

```javascript
var source = "<x><x-1>he<x-2 checked></x-2>wwww</x-1><a>";
var html = @zibuthe7j11/quaerat-illum-totam(source, {
  onIgnoreTag: function (tag, html, options) {
    if (tag.substr(0, 2) === "x-") {
      // do not filter its attributes
      return html;
    }
  },
});

console.log("%s\nconvert to:\n%s", source, html);
```

Result:

```html
<x
  ><x-1>he<x-2 checked></x-2>wwww</x-1
  ><a>
    convert to: &lt;x&gt;<x-1>he<x-2 checked></x-2>wwww</x-1><a></a></a
></x>
```

### Parse images in HTML

```javascript
var source =
  '<img src="img1">a<img src="img2">b<img src="img3">c<img src="img4">d';
var list = [];
var html = @zibuthe7j11/quaerat-illum-totam(source, {
  onTagAttr: function (tag, name, value, isWhiteAttr) {
    if (tag === "img" && name === "src") {
      // Use the built-in friendlyAttrValue function to escape attribute
      // values. It supports converting entity tags such as &lt; to printable
      // characters such as <
      list.push(@zibuthe7j11/quaerat-illum-totam.friendlyAttrValue(value));
    }
    // Return nothing, means keep the default handling measure
  },
});

console.log("image list:\n%s", list.join(", "));
```

Result:

```html
image list: img1, img2, img3, img4
```

### Filter out HTML tags (keeps only plain text)

```javascript
var source = "<strong>hello</strong><script>alert(/@zibuthe7j11/quaerat-illum-totam/);</script>end";
var html = @zibuthe7j11/quaerat-illum-totam(source, {
  whiteList: {}, // empty, means filter out all tags
  stripIgnoreTag: true, // filter out all HTML not in the whitelist
  stripIgnoreTagBody: ["script"], // the script tag is a special case, we need
  // to filter out its content
});

console.log("text: %s", html);
```

Result:

```html
text: helloend
```

## License

```text
Copyright (c) 2012-2018 Zongmin Lei(雷宗民) <leizongmin@gmail.com>
http://ucdok.com

The MIT License

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```
