## `gulp-kdf-pistachio`

A gulp task that compiles pistachio strings of given JS files.

## Example

```coffee
# Gulpfile.coffee
gulp       = require 'gulp'
browserify = require 'browserify'
source     = require 'vinyl-source-stream'
pistachio  = require 'gulp-kdf-pistachio'
gulpBuffer = require 'gulp-buffer'

b = browserify
  cache        : {}
  packageCache : {}
  entries      : ['./src/index.coffee']
  extensions   : ['.coffee', '.js']
.transform 'coffeeify'

runBrowserify = ->
  b.bundle()
    .pipe source('share.js')
    .pipe gulpBuffer()
    .pipe pistachio()
    .pipe gulp.dest('./dist')

gulp.task 'build', -> runBrowserify()
```

## Installation

```
npm install gulp-kdf-pistachio
```

