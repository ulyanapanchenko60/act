![Async Logo](https://raw.githubusercontent.com/caolan/async/master/logo/async-logo_readme.jpg)

[![Build Status via Travis CI](https://travis-ci.org/caolan/async.svg?branch=master)](https://travis-ci.org/caolan/async)
[![Build Status via Azure Pipelines](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)
[![NPM version](https://img.shields.io/npm/v/async.svg)](https://www.npmjs.com/package/async)
[![Coverage Status](https://coveralls.io/repos/caolan/async/badge.svg?branch=master)](https://coveralls.io/r/caolan/async?branch=master)
[![Join the chat at https://gitter.im/caolan/async](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/caolan/async?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)
[![jsDelivr Hits](https://data.jsdelivr.com/v1/package/npm/async/badge?style=rounded)](https://www.jsdelivr.com/package/npm/async)

<!--
|Linux|Windows|MacOS|
|-|-|-|
|[![Linux Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Linux&configuration=Linux%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![Windows Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=Windows&configuration=Windows%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master) | [![MacOS Build Status](https://dev.azure.com/caolanmcmahon/async/_apis/build/status/caolan.async?branchName=master&jobName=OSX&configuration=OSX%20node_10_x)](https://dev.azure.com/caolanmcmahon/async/_build/latest?definitionId=1&branchName=master)| -->

Async is a utility module which provides straight-forward, powerful functions for working with [asynchronous JavaScript](http://caolan.github.io/async/v3/global.html). Although originally designed for use with [Node.js](https://nodejs.org/) and installable via `npm i async`, it can also be used directly in the browser.  A ESM/MJS version is included in the main `async` package that should automatically be used with compatible bundlers such as Webpack and Rollup.

A pure ESM version of Async is available as [`async-es`](https://www.npmjs.com/package/async-es).

For Documentation, visit <https://caolan.github.io/async/>

*For Async v1.5.x documentation, go [HERE](https://github.com/caolan/async/blob/v1.5.2/README.md)*


```javascript
// for use with Node-style callbacks...
var async = require("async");

var obj = {dev: "/dev.json", test: "/test.json", prod: "/prod.json"};
var configs = {};

async.forEachOf(obj, (value, key, callback) => {
    fs.readFile(__dirname + value, "utf8", (err, data) => {
        if (err) return callback(err);
        try {
            configs[key] = JSON.parse(data);
        } catch (e) {
            return callback(e);
        }
        callback();
    });
}, err => {
    if (err) console.error(err.message);
    // configs is now a map of JSON data
    doSomethingWith(configs);
});
```

```javascript
var async = require("async");

// ...or ES2017 async functions
async.mapLimit(urls, 5, async function(url) {
    const response = await fetch(url)
    return response.body
}, (err, results) => {
    if (err) throw err
    // results is now an array of the response bodies
    console.log(results)
})
```

Auto-commit on 2025-02-25 12:13:17 | rand=30709

Auto-commit on 2025-02-25 12:17:57 | rand=41924

Auto-commit on 2025-02-25 12:29:55 | rand=9543

Auto-commit on 2025-02-25 12:42:03 | rand=28812

Auto-commit on 2025-02-25 12:54:06 | rand=81748

Auto-commit on 2025-02-25 13:06:07 | rand=78244

Auto-commit on 2025-02-25 13:18:15 | rand=5957

Auto-commit on 2025-02-25 13:30:22 | rand=9270

Auto-commit on 2025-02-25 13:42:21 | rand=23557

Auto-commit on 2025-02-25 13:54:24 | rand=24449

Auto-commit on 2025-02-25 14:06:25 | rand=61794

Auto-commit on 2025-02-25 14:18:32 | rand=73458

Auto-commit on 2025-02-25 14:30:35 | rand=70273

Auto-commit on 2025-02-25 14:42:43 | rand=83419

Auto-commit on 2025-02-25 14:54:46 | rand=14416

Auto-commit on 2025-02-25 15:06:54 | rand=85083

Auto-commit on 2025-03-06 14:47:51 | rand=15609

Auto-commit on 2025-03-06 14:59:16 | rand=67908

Auto-commit on 2025-03-06 15:10:34 | rand=30647

Auto-commit on 2025-03-06 15:46:58 | rand=43024

Auto-commit on 2025-03-06 15:58:14 | rand=337

Auto-commit on 2025-03-06 16:09:34 | rand=62481

Auto-commit on 2025-03-06 16:20:49 | rand=43194

Auto-commit on 2025-03-06 16:32:07 | rand=60263

Auto-commit on 2025-03-06 16:43:24 | rand=57446

Auto-commit on 2025-03-06 16:54:43 | rand=80530

Auto-commit on 2025-03-06 19:54:55 | rand=90962

Auto-commit on 2025-03-06 20:35:00 | rand=33282

Auto-commit on 2025-03-06 20:46:44 | rand=98746

Auto-commit on 2025-03-06 20:58:07 | rand=58676
