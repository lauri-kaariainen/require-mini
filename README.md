# require-mini [![Build](https://travis-ci.org/just-boris/require-mini.svg?branch=master)](https://travis-ci.org/just-boris/require-mini)

> Tiny replacement of require.js powered by promises

## Overview

It's library with [require.js](https://github.com/jrburke/requirejs/) compatible API and full support of plugins.
We are focusing on small size and use promises which are [native in most browsers](http://caniuse.com/#feat=promises). 
Some of features we don't support for now, but most part of functions works properly. Look at examples in our [tests](test).

Generally you can just switch from original `require.js` to our `require-mini` without any code modifications and will get advantage of lesser code which takes time to load.
[Documentation](http://requirejs.org/docs/api.html) from require.js also applicable here.

Additionaly, because we are using promises, you will get support of asynchronus defines wihout any plugins

```js
define('userData', ['fetch'], function(fetch) {
   return fetch('/api/profile');
});

```

## Caveats

These features is not supported yet, but you can vote for its resolution

* [No CommonJS](https://github.com/just-boris/require-mini/issues/1)
* [No relative paths](https://github.com/just-boris/require-mini/issues/4)
* [No contexts](https://github.com/just-boris/require-mini/issues/8)
* [No data-main attribute support](https://github.com/just-boris/require-mini/issues/9)
* [No define as object](https://github.com/just-boris/require-mini/issues/10)

## Getting started

via Bower

```
bower install require-mini --save
```



## Differences to just-boris's repo

### Newer build
* Update some libraries
* Some CommonJS support. 
### Changes
```js 
define('foobar',function(require,module,exports)) 
``` 
to 
```js 
define('foobar',function(require,exports,module))
```
to make it same as in require.js
   
## Gotchas
### No relative paths! ```require("./foobar")``` is WRONG! Use just ```require("foobar")```


