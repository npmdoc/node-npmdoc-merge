# api documentation for  [merge (v1.2.0)](https://github.com/yeikos/js.merge)  [![npm package](https://img.shields.io/npm/v/npmdoc-merge.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-merge) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-merge.svg)](https://travis-ci.org/npmdoc/node-npmdoc-merge)
#### Merge multiple objects into one, optionally creating a new cloned object. Similar to the jQuery.extend but more flexible. Works in Node.js and the browser.

[![NPM](https://nodei.co/npm/merge.png?downloads=true)](https://www.npmjs.com/package/merge)

[![apidoc](https://npmdoc.github.io/node-npmdoc-merge/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-merge_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-merge/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-merge/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-merge/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "yeikos",
        "url": "http://www.yeikos.com"
    },
    "bugs": {
        "url": "https://github.com/yeikos/js.merge/issues"
    },
    "dependencies": {},
    "description": "Merge multiple objects into one, optionally creating a new cloned object. Similar to the jQuery.extend but more flexible. Works in Node.js and the browser.",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "7531e39d4949c281a66b8c5a6e0265e8b05894da",
        "tarball": "https://registry.npmjs.org/merge/-/merge-1.2.0.tgz"
    },
    "gitHead": "6fc27c23e1ebf54a4f6ba8a7224dd48dfd9faf7c",
    "homepage": "https://github.com/yeikos/js.merge",
    "keywords": [
        "merge",
        "recursive",
        "extend",
        "clone",
        "object",
        "browser"
    ],
    "license": "MIT",
    "main": "merge.js",
    "maintainers": [
        {
            "name": "yeikos",
            "email": "yeikos@gmail.com"
        }
    ],
    "name": "merge",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/yeikos/js.merge.git"
    },
    "scripts": {
        "test": "cd tests; node index.js"
    },
    "version": "1.2.0"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module merge](#apidoc.module.merge)
1.  [function <span class="apidocSignatureSpan">merge.</span>clone (input)](#apidoc.element.merge.clone)
1.  [function <span class="apidocSignatureSpan">merge.</span>recursive (clone)](#apidoc.element.merge.recursive)



# <a name="apidoc.module.merge"></a>[module merge](#apidoc.module.merge)

#### <a name="apidoc.element.merge.clone"></a>[function <span class="apidocSignatureSpan">merge.</span>clone (input)](#apidoc.element.merge.clone)
- description and source-code
```javascript
clone = function (input) {

		var output = input,
			type = typeOf(input),
			index, size;

		if (type === 'array') {

			output = [];
			size = input.length;

			for (index=0;index<size;++index)

				output[index] = Public.clone(input[index]);

		} else if (type === 'object') {

			output = {};

			for (index in input)

				output[index] = Public.clone(input[index]);

		}

		return output;

	}
```
- example usage
```shell
...
		if (type === 'array') {

			output = [];
			size = input.length;

			for (index=0;index<size;++index)

				output[index] = Public.clone(input[index]);

		} else if (type === 'object') {

			output = {};

			for (index in input)
...
```

#### <a name="apidoc.element.merge.recursive"></a>[function <span class="apidocSignatureSpan">merge.</span>recursive (clone)](#apidoc.element.merge.recursive)
- description and source-code
```javascript
recursive = function (clone) {

		return merge(clone === true, true, arguments);

	}
```
- example usage
```shell
...
original = { x: { y: 1 } };
cloned = merge(true, original);
cloned.x.y++;

console.log(original.x.y, cloned.x.y);
// -> 1, 2

console.log(merge.recursive(true, original, { x: { z: 2 } }));
// -> {"x": { "y": 1, "z": 2 } }

'''

## Browser Usage

'''html
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
