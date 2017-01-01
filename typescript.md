# Typescript Style Guide

## Linter :

[tslint](https://github.com/palantir/tslint)

## Config :
[tslint.json](tslint.json)

## Install

### Install tslint

`npm install tslint typescript --save-dev`

In your tslint.json file e.g:
```json
{
  "extends": "tslint:latest"
}
```
### Configuring gulp

* Edit you `gulpfile.js` and add something like this ([source](https://www.npmjs.com/package/gulp-eslint))

```js
var tslint = require('gulp-tslint');

gulp.task('lint.ts', () => {
  return gulp.src([
      'src/**/*.ts'
    ]).pipe(tslint({
      formatter: 'verbose'
    }))
    .pipe(tslint.report());
});
```

Run `gulp lint`

## How to integrate the linter in editors

* Atom : [atom-tslint](https://atom.io/packages/linter-tslint)

## We could look at these styles :
* [ESLint rules for TSLint](https://github.com/buzinas/tslint-eslint-rules)
* [Excel Micro TypeScript Style Guide](https://github.com/excelmicro/typescript)
