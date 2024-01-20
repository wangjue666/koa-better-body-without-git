# koa-better-body-without-git

This is a substitute for `koa-better-body`, but without `koa-body-parser`. Faster download speed

## Why?

Due to the dependency source of `koa-body-parsers` in GitHub, Unable to adapt to CDN nodes, resulting
in particularly slow download speed! Even unable to download! And the author of `koa-better-body` no longer maintains the project..., so kill it~

```
 "dependencies": {
    "extend-shallow": "^3.0.2",
    "formidable": "^1.2.1",
    "koa-body-parsers": "tunnckocore/body-parsers#patch-1"
  },
```

## install

```
npm i koa-better-body-without-git
```

## before

```
const body = require('koa-better-body');
const convert = require('koa-convert');

server.use(
    convert(body({
        uploadDir: config.uploadDir,
        keepExtensions: true,
        formLimit: "5mb",
        jsonLimit: "5mb"
    }))
)

```

## now

```
const body = require('koa-better-body-without-git');
const convert = require('koa-convert');

// here is call body.default
server.use(
    convert(body.default({
        uploadDir: config.uploadDir,
        keepExtensions: true,
        formLimit: "5mb",
        jsonLimit: "5mb"
    }))
)
```
