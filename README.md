# api documentation for  [diskusage (v0.2.1)](https://github.com/jduncanator/node-diskusage)  [![npm package](https://img.shields.io/npm/v/npmdoc-diskusage.svg?style=flat-square)](https://www.npmjs.org/package/npmdoc-diskusage) [![travis-ci.org build-status](https://api.travis-ci.org/npmdoc/node-npmdoc-diskusage.svg)](https://travis-ci.org/npmdoc/node-npmdoc-diskusage)
#### Get total diskspace and free diskspace using bindings around platform specific calls.

[![NPM](https://nodei.co/npm/diskusage.png?downloads=true)](https://www.npmjs.com/package/diskusage)

[![apidoc](https://npmdoc.github.io/node-npmdoc-diskusage/build/screenCapture.buildNpmdoc.browser._2Fhome_2Ftravis_2Fbuild_2Fnpmdoc_2Fnode-npmdoc-diskusage_2Ftmp_2Fbuild_2Fapidoc.html.png)](https://npmdoc.github.io/node-npmdoc-diskusage/build/apidoc.html)

![npmPackageListing](https://npmdoc.github.io/node-npmdoc-diskusage/build/screenCapture.npmPackageListing.svg)

![npmPackageDependencyTree](https://npmdoc.github.io/node-npmdoc-diskusage/build/screenCapture.npmPackageDependencyTree.svg)



# package.json

```json

{
    "author": {
        "name": "jduncanator"
    },
    "bugs": {
        "url": "https://github.com/jduncanator/node-diskusage/issues"
    },
    "dependencies": {
        "nan": "^2.5.0"
    },
    "description": "Get total diskspace and free diskspace using bindings around platform specific calls.",
    "devDependencies": {},
    "directories": {},
    "dist": {
        "shasum": "222047a3a28266ae77b8275462ac381f8347a3e6",
        "tarball": "https://registry.npmjs.org/diskusage/-/diskusage-0.2.1.tgz"
    },
    "gitHead": "a34d2367d0bc727490ff0b75c63576a802fd83f2",
    "gypfile": true,
    "homepage": "https://github.com/jduncanator/node-diskusage",
    "keywords": [
        "disk",
        "usage",
        "df",
        "hdd",
        "ssd",
        "diskusage",
        "df",
        "free",
        "space"
    ],
    "license": "MIT",
    "main": "index.js",
    "maintainers": [
        {
            "name": "jduncanator",
            "email": "jduncanator@hotmail.com"
        }
    ],
    "name": "diskusage",
    "optionalDependencies": {},
    "readme": "ERROR: No README data found!",
    "repository": {
        "type": "git",
        "url": "git+https://github.com/jduncanator/node-diskusage.git"
    },
    "scripts": {
        "install": "node-gyp rebuild"
    },
    "typings": "index.d.ts",
    "version": "0.2.1"
}
```



# <a name="apidoc.tableOfContents"></a>[table of contents](#apidoc.tableOfContents)

#### [module diskusage](#apidoc.module.diskusage)
1.  [function <span class="apidocSignatureSpan">diskusage.</span>check (path, callback)](#apidoc.element.diskusage.check)
1.  [function <span class="apidocSignatureSpan">diskusage.</span>checkSync ()](#apidoc.element.diskusage.checkSync)



# <a name="apidoc.module.diskusage"></a>[module diskusage](#apidoc.module.diskusage)

#### <a name="apidoc.element.diskusage.check"></a>[function <span class="apidocSignatureSpan">diskusage.</span>check (path, callback)](#apidoc.element.diskusage.check)
- description and source-code
```javascript
check = function (path, callback) {
    try {
        callback(undefined, native.getDiskUsage(path));
    }
    catch (error) {
        callback(error, undefined);
    }
}
```
- example usage
```shell
...
--------

''' js
const disk = require('diskusage');

let path = os.platform() === 'win32' ? 'c:' : '/';

disk.check(path, function(err, info) {
	if (err) {
		console.log(err);
	} else {
		console.log(info.available);
		console.log(info.free);
		console.log(info.total);
	}
...
```

#### <a name="apidoc.element.diskusage.checkSync"></a>[function <span class="apidocSignatureSpan">diskusage.</span>checkSync ()](#apidoc.element.diskusage.checkSync)
- description and source-code
```javascript
function getDiskUsage() { [native code] }
```
- example usage
```shell
...
		console.log(info.available);
		console.log(info.free);
		console.log(info.total);
	}
});

try {
	let info = disk.checkSync(path);
	console.log(info.available);
	console.log(info.free);
	console.log(info.total);
}
catch (err) {
	console.log(err);
}
...
```



# misc
- this document was created with [utility2](https://github.com/kaizhu256/node-utility2)
