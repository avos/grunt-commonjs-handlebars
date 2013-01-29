# grunt-commonjs-handlebars [![Build Status](https://secure.travis-ci.org/avos/grunt-commonjs-handlebars.png?branch=master)](http://travis-ci.org/avos/grunt-contrib-handlebars)

> Precompile Handlebars templates into commonjs modules.

## Getting Started
If you haven't used [grunt][] before, be sure to check out the [Getting Started][] guide, as it explains how to create a [gruntfile][Getting Started] as well as install and use grunt plugins. Once you're familiar with that process, install this plugin with this command:

```shell
npm install grunt-commonjs-handlebars --save-dev
```
[grunt]: http://gruntjs.com/
[Getting Started]: https://github.com/gruntjs/grunt/blob/devel/docs/getting_started.md

## Handlebars task
_Run this task with the `grunt handlebars` command._

_This task is a [multi task][] so any targets, files and options should be specified according to the [multi task][] documentation._
[multi task]: https://github.com/gruntjs/grunt/wiki/Configuring-tasks

### Usage Examples

```js
handlebars: {
  dist: {
    files: {
      "path/to/result.js": "path/to/source.hbs",
      "path/to/another.js": ["path/to/sources/*.hbs", "path/to/more/*.hbs"]
    }
  },

  //This is an example to convert each .hbs into its own .js file.
  dev: {
    files: grunt.file.expandMapping(['app/views/templates/**/*.hbs'], 'tmp/views/templates/', {
      rename: (destBase, destPath) ->
        return destBase + destPath.split('app/views/templates/')[1].replace /\.hbs$/, '.js'
    })
  }
}
```

## Release History

 * 2013-01-22   v0.1.0rc7   Initial release.

## License
Copyright (c) 2012 Team Delicious, AVOS Systems Inc., Tim Branyen, contributors
Licensed under the MIT license.
