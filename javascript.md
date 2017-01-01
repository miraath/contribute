# Javascript Style Guide

## We currently use these styles :
* For ES6 : [Airbnb JavaScript Style Guide()](http://airbnb.io/javascript/)
* For ES5 : [Airbnb JavaScript Style Guide() ES5](https://github.com/airbnb/javascript/tree/es5-deprecated/es5)

## Linter :

[eslint](https://github.com/eslint/eslint)

## Config :
[.eslintrc](.eslintrc)

## Install eslint with airbnb config in your project

### For ES6

If you use ES6 you should install follow these steps :

* Add a `.eslintrc` file to your project root folder containing the following :

```json
{
  "extends": "airbnb"
}
```

* Run the following code in console in your project folder ([source](https://www.npmjs.com/package/eslint-config-airbnb))

```bash
(
  export PKG=eslint-config-airbnb;
  npm info "$PKG@latest" peerDependencies --json | command sed 's/[\{\},]//g ; s/: /@/g' | xargs npm install --save-dev "$PKG@latest"
)
```

### For ES5

If you use ES5 you should install follow these steps :

* Add a `.eslintrc` file to your project root folder containing the following :

```json
{
  "extends": "eslint-config-airbnb-es5"
}
```

* Install eslint-config-airbnb-es5 and dependencies by running the following code in console in your project folder ([source](https://www.npmjs.com/package/eslint-config-airbnb-es5))

`npm install --save-dev eslint eslint-config-airbnb-es5 babel-eslint@6.x eslint-plugin-react`

## Configuring gulp
* install `gulp-eslint` : `npm install gulp-eslint --save-dev`

* Edit you `gulpfile.js` and add something like the following ([source](https://www.npmjs.com/package/gulp-eslint))

```js
const gulp = require('gulp');
const eslint = require('gulp-eslint');

gulp.task('lint', () => {
    return gulp.src(['**/*.js','!node_modules/**'])
        // eslint() attaches the lint output to the "eslint" property
        // of the file object so it can be used by other modules.
        .pipe(eslint())
        // eslint.format() outputs the lint results to the console.
        // Alternatively use eslint.formatEach() (see Docs).
        .pipe(eslint.format())
        // To have the process exit with an error code (1) on
        // lint error, return the stream and pipe to failAfterError last.
        .pipe(eslint.failAfterError());
});

gulp.task('default', ['lint'], function () {
    // This will only run if the lint task is successful...
});
```

Run `gulp lint`


## How to integrate the linter in editors

* Atom : [atom-eslint package](https://atom.io/packages/linter-eslint)
