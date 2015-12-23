# gulp-i18n-localize [![Build Status](https://travis-ci.org/filaraujo/gulp-i18n-localize.svg?branch=master)](https://travis-ci.org/filaraujo/gulp-i18n-localize)

> My exquisite gulp plugin


## Install

```
$ npm install --save-dev gulp-i18n-localize
```


## Usage

```js
var gulp = require('gulp');
var i18n = require('gulp-i18n-localize');

gulp.task('default', function () {
	return gulp.src('src/index.html')
		.pipe(i18n({
			locales: ['en-US'],
			localeDir: './locales'
		}))
		.pipe(gulp.dest('dist'));
});
```


## API

### i18n(options)

#### options

##### delimeters

Type: `array`
Default: `['${{', '}}$']`

Sets the delimeters to search assets files and replace with translated content.
By default, it will match `${{` and `$}}`.

delimeters				| matches
--------------- 	| -------------
`${{` `}}$`				| `${{ foo.bar }}$`
`^{` `}^`					| `^{ foo.bar }^`
`translate(` `)`	| `t(foo.bar)`  but why would you do this!!!


---

##### localeDir

Type: `array`
`Required`

Location of translation files. This is a required field.

---

##### locales

Type: `array`
Default: `['en-US']`

Locales to translate, should match `localDir` subfolders.

---

##### schema

Type: `string`
Default: `directory`

Sets the schema to be used for naming translated assets.

schema			| output name
----------- | -------------
`directory`	| `/en-US/index.html`
`suffix`  	| `/index-en-US.html`



## License

MIT © [Filipe Araujo](https://github.com/filaraujo)
