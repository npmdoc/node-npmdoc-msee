# api documentation for  [msee (v0.3.3)](https://github.com/firede/msee#readme)  [![npm package](https://img.shields.io/npm/v/npmdoc-msee.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-msee) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-msee.svg)](https://travis-ci.org/npmdoc/node-npmdoc-msee)
#### Msee is a command-line tool to read Markdown file in your terminal, and it's a library help your command-line software to output readable markdown content.

[![NPM](https://nodei.co/npm/msee.png?downloads=true)](https://www.npmjs.com/package/msee)

[![apidoc](https://npmdoc.github.io/node-npmdoc-msee/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-msee_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-msee/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-msee/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-msee/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "Firede",
        "email": "firede@firede.us"
    },
    "bin": {
        "msee": "./bin/msee"
    },
    "bugs": {
        "url": "https://github.com/firede/msee/issues"
    },
    "contributors": [
        {
            "name": "Martin Heidegger",
            "email": "martin.heidegger@gmail.com"
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
            "name": "firede",
            "email": "firede@firede.us"
        },
        {
            "name": "leichtgewicht",
            "email": "martin.heidegger@gmail.com"
        }
    ],
    "name": "msee",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
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



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module msee](#apidoc.module.msee)
1.  [function <span class="apidocSignatureSpan">msee.</span>parse (text, options)](#apidoc.element.msee.parse)
1.  [function <span class="apidocSignatureSpan">msee.</span>parseFile (file, options)](#apidoc.element.msee.parseFile)
1.  object <span class="apidocSignatureSpan">msee.</span>syntaxColor

#### [module msee.syntaxColor](#apidoc.module.msee.syntaxColor)
1.  [function <span class="apidocSignatureSpan">msee.syntaxColor.</span>_default (s)](#apidoc.element.msee.syntaxColor._default)
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Block
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Boolean
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Identifier
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Keyword
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Line
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Null
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Numeric
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>Punctuator
1.  object <span class="apidocSignatureSpan">msee.syntaxColor.</span>String



# <a name="apidoc.module.msee"></a>[module msee](#apidoc.module.msee)

#### <a name="apidoc.element.msee.parse"></a>[function <span class="apidocSignatureSpan">msee.</span>parse (text, options)](#apidoc.element.msee.parse)
- description and source-code
```javascript
parse = function (text, options) {
    tokens = marked.lexer(text);
    inline = new marked.InlineLexer(tokens.links);
    options = xtend(defaultOptions, options);

    var outputArr = [];
    var output;

    if (options.maxWidth !== -1 && options.width > options.maxWidth) {
        options.width = options.maxWidth
    }

    while (next()) {
        outputArr.push(processToken(options));
    }

    if (options.collapseNewlines) {
        output = outputArr.join('').replace(/\n\n\n/g, '\n\n');
    }

    tokens = null;
    token = null;

    return output;
}
```
- example usage
```shell
...

## API

'''javascript
var msee = require('msee');

// parse markdown text
msee.parse('> hello world!');

// parse markdown file
msee.parseFile('~/doc/readme.md');
'''

## Contributors
...
```

#### <a name="apidoc.element.msee.parseFile"></a>[function <span class="apidocSignatureSpan">msee.</span>parseFile (file, options)](#apidoc.element.msee.parseFile)
- description and source-code
```javascript
parseFile = function (file, options) {
    var filePath = path.resolve(__dirname, file);
    var ret = '';

    try {
        var text = fs.readFileSync(filePath).toString();
        ret = exports.parse(text, options);
    }
    catch (e) {
        throw e;
    }

    return ret;
}
```
- example usage
```shell
...
'''javascript
var msee = require('msee');

// parse markdown text
msee.parse('> hello world!');

// parse markdown file
msee.parseFile('~/doc/readme.md');
'''

## Contributors

https://github.com/firede/msee/graphs/contributors

## License
...
```



# <a name="apidoc.module.msee.syntaxColor"></a>[module msee.syntaxColor](#apidoc.module.msee.syntaxColor)

#### <a name="apidoc.element.msee.syntaxColor._default"></a>[function <span class="apidocSignatureSpan">msee.syntaxColor.</span>_default (s)](#apidoc.element.msee.syntaxColor._default)
- description and source-code
```javascript
_default = function (s) {
  return o + s + c;
}
```
- example usage
```shell
n/a
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
