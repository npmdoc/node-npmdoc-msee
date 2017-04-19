# npmdoc-msee

#### api documentation for  [msee (v0.3.3)](https://github.com/firede/msee#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-msee.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-msee) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-msee.svg)](https://travis-ci.org/npmdoc/node-npmdoc-msee)

#### Msee is a command-line tool to read Markdown file in your terminal, and it's a library help your command-line software to output readable markdown content.

[![NPM](https://nodei.co/npm/msee.png?downloads=true&downloadRank=true&stars=true)](https://www.npmjs.com/package/msee)

- [https://npmdoc.github.io/node-npmdoc-msee/build/apidoc.html](https://npmdoc.github.io/node-npmdoc-msee/build/apidoc.html)

[![apidoc](https://npmdoc.github.io/node-npmdoc-msee/build/screenCapture.buildCi.browser.%252Ftmp%252Fbuild%252Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-msee/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-msee/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-msee/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Firede"
    },
    "bin": {
        "msee": "./bin/msee"
    },
    "bugs": {
        "url": "https://github.com/firede/msee/issues"
    },
    "contributors": [
        {
            "name": "Martin Heidegger"
        }
    ],
    "dependencies": {
        "ansi-regex": "^2.0.0",
        "ansicolors": "^0.3.2",
        "cardinal": "^0.7.1",
        "chalk": "^1.1.1",
        "combined-stream-wait-for-it": "^1.1.0",
        "entities": "^1.1.1",
        "marked": "^0.3.5",
        "nopt": "^3.0.4",
        "table-header": "^0.2.2",
        "text-table": "^0.2.0",
        "through2": "^2.0.3",
        "wcstring": "^2.1.0",
        "xtend": "^4.0.0"
    },
    "description": "Msee is a command-line tool to read Markdown file in your terminal, and it's a library help your command-line software to output readable markdown content.",
    "devDependencies": {
        "stream-to-string": "^1.1.0",
        "tap": "^5.7.1"
    },
    "directories": {},
    "dist": {
        "shasum": "be36b6d08eb5e2548a7b1dda7a0d45b6888eeced",
        "tarball": "https://registry.npmjs.org/msee/-/msee-0.3.3.tgz"
    },
    "gitHead": "b088cd617126c536bfbb27eed8efa1bd95223ff7",
    "homepage": "https://github.com/firede/msee#readme",
    "keywords": [
        "markdown",
        "terminal",
        "reader",
        "console",
        "shell",
        "colors",
        "highlight"
    ],
    "license": "MIT",
    "main": "./lib/msee.js",
    "maintainers": [
        {
            "name": "firede"
        },
        {
            "name": "leichtgewicht"
        }
    ],
    "name": "msee",
    "optionalDependencies": {},
    "repository": {
        "type": "git",
        "url": "git://github.com/firede/msee.git"
    },
    "scripts": {
        "test": "env FORCE_COLOR=true tap --lines=85 test/**/*.js"
    },
    "version": "0.3.3"
}
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
