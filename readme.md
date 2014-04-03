# [gulp](http://gulpjs.com)-nunjucks [![Build Status](https://travis-ci.org/sindresorhus/gulp-nunjucks.svg?branch=master)](https://travis-ci.org/sindresorhus/gulp-nunjucks)

> Precompile [Nunjucks](http://jlongster.github.io/nunjucks/) templates

*Issues with the output should be reported on the Nunjucks [issue tracker](https://github.com/jlongster/nunjucks/issues).*


## Install

```bash
$ npm install --save-dev gulp-nunjucks
```


## Usage

```js
var gulp = require('gulp');
var nunjucks = require('gulp-nunjucks');

gulp.task('default', function () {
	gulp.src('templates/list.html')
		.pipe(nunjucks())
		.pipe(gulp.dest('dist'));
});
```


## API

### nunjucks(options)

Same options as [`nunjucks.precompile()`](http://jlongster.github.io/nunjucks/api.html#precompile) except for `name`.

#### options.name

Type: `Function`  
Default: *Relative template path. Example: `templates/list.html`*

You can override the default behavior by supplying a function which gets the current [File](https://github.com/wearefractal/vinyl#constructoroptions) object and is expected to return the name.

Example:

```js
{
	name: function (file) {
		return 'tpl-' + file.relative;
	}
}
```


## License

[MIT](http://opensource.org/licenses/MIT) © [Sindre Sorhus](http://sindresorhus.com)
