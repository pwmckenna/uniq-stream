uniq-stream
====
[![Build Status](https://travis-ci.org/jarofghosts/uniq-stream.png?branch=master)](https://travis-ci.org/jarofghosts/uniq-stream)

a stream that acts like `uniq`

## usage

pipe it data and it pipes out de-duped (by line) data

#### example

```js
var uniq = require('uniq'),
    split = require('split'),
    fs = require('fs')

fs.createReadStream('dupe-ridden-file.txt')
  .pipe(split())
  .pipe(uniq())
  .pipe(fs.createWriteStream('clean-file.txt'))
```

## options

uniq-stream accepts an options object as a first parameter, the acceptable
options are outlined below along with their defaults.

```js
{
  global: false, // de-dupe data globally rather than line-wise
  ignoreCase: false, // case insensitive comparison
  skip: 0, // ignore first (value) characters of input string for comparison
  inverse: false // only emit duplicated lines
}
```

## license

MIT
