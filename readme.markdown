# subarg

parse arguments with recursive contexts using
[minimist](https://npmjs.org/package/minimist)

[![build status](https://secure.travis-ci.org/minimistjs/subarg.png)](http://travis-ci.org/minimistjs/subarg)

This module is useful if you need to pass arguments into a piece of code without coordinating ahead of time with the main program, like with a plugin system.

**Note**: This repo is a reconstruction of https://github.com/substack/subarg, via the [Internet Archive](https://web.archive.org/web/20201110211117/https://github.com/substack/subarg) and various forks.

# example

``` js
var subarg = require('@minimistjs/subarg');
var argv = subarg(process.argv.slice(2));
console.log(argv);
```

Contexts are denoted with square brackets:

```
$ node example/show.js rawr --beep [ boop -a 3 ] -n4 --robots [ -x 8 -y 6 ]
{ _: [ 'rawr' ],
  beep: { _: [ 'boop' ], a: 3 },
  n: 4,
  robots: { _: [], x: 8, y: 6 } }
```

# methods

``` js
var subarg = require('subarg')
```

## var argv = subarg(args, opts)

Parse the arguments array `args`, passing `opts` to
[minimist](https://npmjs.org/package/minimist).

An opening `[` in the `args` array creates a new context and a `]` closes a
context. Contexts may be nested.

# install

With [npm](https://npmjs.org) do:

```
npm install subarg
```

# license

MIT
