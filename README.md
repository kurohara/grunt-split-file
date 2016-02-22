# grunt-split-file

> Split specified files into multiple parts.

## Getting Started
This plugin requires Grunt `~0.4.5`

If you haven't used [Grunt](http://gruntjs.com/) before, be sure to check out the [Getting Started](http://gruntjs.com/getting-started) guide, as it explains how to create a [Gruntfile](http://gruntjs.com/sample-gruntfile) as well as install and use Grunt plugins. Once you're familiar with that process, you may install this plugin with this command:

```shell
npm install grunt-split-file --save-dev
```

Once the plugin has been installed, it may be enabled inside your Gruntfile with this line of JavaScript:

```js
grunt.loadNpmTasks('grunt-split-file');
```

## The "splitfile" task

### Overview
In your project's Gruntfile, add a section named `splitfile` to the data object passed into `grunt.initConfig()`.


```js
grunt.initConfig({
  splitfile: {
    options: {
      // Task-specific options go here.
    },
    your_target: {
      // Target-specific file lists and/or options go here.
    },
  },
});
```

### Options

#### options.separator
Type: `String` or `RegExp`  
Default value: no default  

Separator string or regular expression to split into multiple parts from contents of src files.  

#### options.prefix
Type: `String`  or `Array of String`  
Default value: no default value  

Used as the prefix of destination file name.

#### options.suffix
Type: `String`  
Default value: no defalt value

Used as the suffix of destination filename.  
If not present, the suffix of source file name is used instead.  

### Usage Examples

#### Single source file to multiple output files.

```js
grunt.initConfig({
  splitfile: {
    options: {
      separator: 'abc',
      prefix: [ "1", "2" ]
    },
    files: {
      'destdir': 'src/srcfile.txt',
    },
  },
});
```

src/srcfile.txt  
```
aaaaaaaaa
abc
bbbbbbbbbb
```

destdir/1.txt
```
aaaaaaaaa
```

destdir/2.txt
```
bbbbbbbbbb
```

## Contributing
In lieu of a formal styleguide, take care to maintain the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [Grunt](http://gruntjs.com/).

## Release History
1.0.0 May 21 2015
