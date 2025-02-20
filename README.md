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

Auto-commit on 2025-02-19 11:18:45 | rand=76271

Auto-commit on 2025-02-19 18:30:08 | rand=54552

Auto-commit on 2025-02-19 18:43:07 | rand=99979

Auto-commit on 2025-02-19 18:56:04 | rand=91843

Auto-commit on 2025-02-19 19:08:52 | rand=33856

Auto-commit on 2025-02-19 19:21:52 | rand=96064

Auto-commit on 2025-02-19 19:34:44 | rand=15098

Auto-commit on 2025-02-19 19:47:37 | rand=39877

Auto-commit on 2025-02-19 20:00:35 | rand=13971

Auto-commit on 2025-02-19 20:13:29 | rand=14922

Auto-commit on 2025-02-19 20:26:29 | rand=52433

Auto-commit on 2025-02-19 20:39:21 | rand=41555

Auto-commit on 2025-02-19 20:52:15 | rand=40519

Auto-commit on 2025-02-19 21:05:16 | rand=8779

Auto-commit on 2025-02-19 21:18:10 | rand=98688

Auto-commit on 2025-02-19 21:31:08 | rand=95919

Auto-commit on 2025-02-20 09:36:24 | rand=12933

Auto-commit on 2025-02-20 14:12:12 | rand=93851

Auto-commit on 2025-02-20 14:24:18 | rand=10171

Auto-commit on 2025-02-20 14:36:27 | rand=45597

Auto-commit on 2025-02-20 14:48:28 | rand=46990

Auto-commit on 2025-02-20 15:00:25 | rand=45840

Auto-commit on 2025-02-20 15:12:32 | rand=7857

Auto-commit on 2025-02-20 15:24:32 | rand=30600
