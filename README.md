# gulp-img-base64

[![NPM version][npm-image]][npm-url]
[![Build Status][travis-image]][travis-url]
[![Coverage Status][coveralls-image]][coveralls-url]

A simple gulp plugin, used to transform image into base64 string.

## Install
```
npm install gulp-img-base64
```

## Usage
```javascript
var tobase64 = require("gulp-img-base64");
tobase64(options);
```

### Example
```javascript
var tobase64 = require("gulp-img-base64");
gulp.task('build-html' , function(){
  return gulp.src("./html-init/**/*.html")
      .pipe(tobase64({
          maxsize:0.5,        
          ignore:'image_loading.png',
          pathrep: {
              reg:/\/public\/bizapp\d*\//g ,
              rep:'./public/'
          }
      }))
      .pipe(gulp.dest("./html"))
});
```

## API

### maxsize
The max size of images for compiling, the default value is 1 and the unit is 'KB'

### ignore
Ignore files, it can be string, array or regular. <br>
```
'image' , ['image','abc'] or /\/abc\//g
```

### pathrep
Transform file path into readable path like this :
```
/public/bizapp1007/image.png ==> ./public/image.png
```

## Running test
```
make test
```

## License
MIT

[npm-url]: https://npmjs.org/package/gulp-img-base64
[npm-image]: http://img.shields.io/npm/v/gulp-img-base64.svg?style=flat-square
[travis-url]: https://travis-ci.org/whxaxes/gulp-img-base64
[travis-image]: http://img.shields.io/travis/whxaxes/gulp-img-base64.svg?style=flat-square
[coveralls-url]: https://coveralls.io/r/whxaxes/gulp-img-base64
[coveralls-image]: https://img.shields.io/coveralls/whxaxes/gulp-img-base64.svg?style=flat-square
