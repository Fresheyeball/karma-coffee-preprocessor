# karma-coffee-preprocessor

> Preprocessor to compile CoffeeScript on the fly.

## Installation

The easiest way is to keep `karma-coffee-preprocessor` as a devDependency in your `package.json`.
```json
{
  "devDependencies": {
    "karma": "~0.10",
    "karma-coffee-preprocessor": "~0.1"
  }
}
```

You can simple do it by:
```bash
npm install karma-coffee-preprocessor --save-dev
```

## Configuration
Following code shows the default configuration...
```js
// karma.conf.js
module.exports = function(config) {
  config.set({
    preprocessors: {
      '**/*.coffee': ['coffee']
    },

    coffeePreprocessor: {
      // options passed to the coffee compiler
      options: {
        bare: true,
        sourceMap: false
      },
      // transforming the filenames
      transformPath: function(path) {
        return path.replace(/\.coffee$/, '.js');
      }
    },

    // make sure to include the .coffee files not the compiled .js files 
    files: {
      '**/*.coffee'
    }
  });
};
```

If you set the `sourceMap` coffee compiler option to `true` then the generated source map will be inlined as a data-uri.

----

For more information on Karma see the [homepage].


[homepage]: http://karma-runner.github.com
