# karma-iced-preprocessor

> Preprocessor to compile IcedCoffeeScript on the fly.

## Installation

**This plugin ships with Karma by default, so you don't need to install it, it should just work ;-)**

The easiest way is to keep `karma-iced-preprocessor` as a devDependency in your `package.json`.
```json
{
  "devDependencies": {
    "karma": "~0.10",
    "karma-iced-preprocessor": "0.1.0-g"
  }
}
```

You can simple do it by:
```bash
npm install karma-iced-preprocessor --save-dev
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
        sourceMap: false,
        runtime: 'inline'
      },
      // transforming the filenames
      transformPath: function(path) {
        return path.replace(/\.js$/, '.coffee');
      }
    }
  });
};
```

If you set the `sourceMap` coffee compiler option to `true` then the generated source map will be inlined as a data-uri.

----

For more information on Karma see the [homepage].


[homepage]: http://karma-runner.github.com
