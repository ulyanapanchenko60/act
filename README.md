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

Auto-commit on 2025-02-22 00:33:24 | rand=16213

Auto-commit on 2025-02-22 00:45:26 | rand=82857

Auto-commit on 2025-02-22 00:57:27 | rand=8972

Auto-commit on 2025-02-22 01:09:30 | rand=26747

Auto-commit on 2025-02-22 01:21:38 | rand=76897

Auto-commit on 2025-02-22 01:33:37 | rand=32697

Auto-commit on 2025-02-22 01:45:42 | rand=39330

Auto-commit on 2025-02-22 01:57:42 | rand=25663

Auto-commit on 2025-02-22 02:09:50 | rand=46221

Auto-commit on 2025-02-22 02:21:56 | rand=82074

Auto-commit on 2025-02-22 02:34:04 | rand=76752

Auto-commit on 2025-02-22 02:46:09 | rand=44333

Auto-commit on 2025-02-22 02:58:08 | rand=32191

Auto-commit on 2025-02-22 03:10:26 | rand=36700

Auto-commit on 2025-02-22 14:50:22 | rand=42958

Auto-commit on 2025-02-22 15:02:31 | rand=28462

Auto-commit on 2025-02-22 15:14:36 | rand=25134

Auto-commit on 2025-02-22 15:26:42 | rand=23313

Auto-commit on 2025-02-22 15:38:42 | rand=39363

Auto-commit on 2025-02-22 15:50:48 | rand=7698

Auto-commit on 2025-02-22 16:02:54 | rand=28116

Auto-commit on 2025-02-22 16:14:52 | rand=83025

Auto-commit on 2025-02-22 16:26:54 | rand=91623

Auto-commit on 2025-02-22 16:38:54 | rand=6800

Auto-commit on 2025-02-22 16:50:58 | rand=49562

Auto-commit on 2025-02-22 17:02:58 | rand=32898

Auto-commit on 2025-02-22 17:15:07 | rand=22080

Auto-commit on 2025-02-22 17:27:09 | rand=93535

Auto-commit on 2025-02-22 17:39:14 | rand=92851

Auto-commit on 2025-02-24 13:54:02 | rand=88931

Auto-commit on 2025-02-24 14:06:02 | rand=43088

Auto-commit on 2025-02-24 14:18:02 | rand=55336

Auto-commit on 2025-02-24 14:30:10 | rand=63604

Auto-commit on 2025-02-24 14:42:16 | rand=96368

Auto-commit on 2025-02-24 14:54:16 | rand=10776

Auto-commit on 2025-02-24 15:06:25 | rand=71968

Auto-commit on 2025-02-24 15:18:27 | rand=73854

Auto-commit on 2025-02-24 15:30:35 | rand=36579

Auto-commit on 2025-02-24 15:42:48 | rand=42870

Auto-commit on 2025-02-24 15:54:56 | rand=52154

Auto-commit on 2025-02-24 16:06:57 | rand=54439

Auto-commit on 2025-02-24 16:18:54 | rand=8344

Auto-commit on 2025-02-24 16:31:00 | rand=24868

Auto-commit on 2025-02-24 16:43:03 | rand=27065

Auto-commit on 2025-02-24 17:55:16 | rand=17463

Auto-commit on 2025-02-24 18:07:16 | rand=64779

Auto-commit on 2025-02-24 18:19:22 | rand=24226

Auto-commit on 2025-02-24 18:31:25 | rand=72836

Auto-commit on 2025-02-24 18:43:37 | rand=44053

Auto-commit on 2025-02-24 18:55:40 | rand=17725

Auto-commit on 2025-02-24 19:07:52 | rand=70865

Auto-commit on 2025-02-24 19:19:53 | rand=74820

Auto-commit on 2025-02-24 19:31:55 | rand=81395
