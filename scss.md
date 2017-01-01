# SCSS Style Guide

## We currently use these styles :
[Airbnb CSS / Sass Styleguide](https://github.com/airbnb/css)

## Linter :

[eslint](https://github.com/eslint/eslint)

## Config :
[.sass-lint.yml](.sass-lint.yml)
[Source of config file](https://github.com/airbnb/css/pull/34)

## Install gulp-sass-lint in your project
source : [gulp-sass-lint on npmjs](https://www.npmjs.com/package/gulp-sass-lint)

add [.sass-lint.yml](.sass-lint.yml) in your project folder

`npm install gulp-sass-lint --save-dev`

Add something like this this to you gulpfile.js
```js
'use strict';

var gulp = require('gulp'),
    sassLint = require('gulp-sass-lint');

gulp.task('default', function () {
  return gulp.src('sass/**/*.s+(a|c)ss')
    .pipe(sassLint())
    .pipe(sassLint.format())
    .pipe(sassLint.failOnError())
});
```

## How to integrate the linter in editors

* Atom : [linter-sass-lint plugin](https://atom.io/packages/linter-sass-lint)
