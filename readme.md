# captcha-solver

> Library for automating captcha verification.

[![NPM](https://img.shields.io/npm/v/captcha-solver.svg)](https://www.npmjs.com/package/captcha-solver) [![Build Status](https://travis-ci.com/transitive-bullshit/captcha-solver.svg?branch=master)](https://travis-ci.com/transitive-bullshit/captcha-solver) [![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)

## Status

This project is fully functional both as a [library](packages/captcha-solver) and [CLI](packages/captcha-solver-cli). We currently only support one captcha-solver-provider, powered by [anti-captcha](https://anti-captcha.com).

## Packages

-   [captcha-solver](packages/captcha-solver) - Library for automating captcha verification.
-   [captcha-solver-cli](packages/captcha-solver-cli) - CLI for automating captcha verification.
-   [captcha-solver-provider](packages/captcha-solver-provider) - Abstract base class for captcha solver providers.
    -   [captcha-solver-provider-anti-captcha](packages/captcha-solver-provider-anti-captcha) - Captcha solver provider for the [anti-captcha](https://anti-captcha.com) service.
    -   [captcha-solver-provider-browser](packages/captcha-solver-provider-browser) - Captcha solver provider for a local, browser-based, manual solver.

## Usage

```bash
  Usage: index [options] [command]

  Options:

    -V, --version                       output the version number
    -i, --image <path>                  path or url of image to solve
    -t, --type <string>                 type of captcha to solve (default: image-to-text)
    -k, --key <string>                  api key for provider
    -P, --provider <provider>           provider to use for solving (default: anti-captcha)
    -h, --help                          output usage information

  Commands:

    create-task
    get-task-result [options] <taskId>
    solve [options]
```

## API

<!-- Generated by documentation.js. Update this documentation by updating the source code. -->

#### Table of Contents

-   [CaptchaSolver](#captchasolver)
    -   [provider](#provider)
    -   [createTask](#createtask)
    -   [getTaskResult](#gettaskresult)

### [CaptchaSolver](https://github.com/transitive-bullshit/captcha-solver/blob/170214d0031b20cd05080088b16434b7b900386d/packages/captcha-solver/index.js#L19-L100)

Main entrypoint for solving captchas.

Type: `function (provider, opts)`

-   `provider` **([string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) | CaptchaSolverProvider)** Name of built-in provider or an instance of
    a custom provider to use for solving.
-   `opts`   (optional, default `{}`)

* * *

#### [provider](https://github.com/transitive-bullshit/captcha-solver/blob/170214d0031b20cd05080088b16434b7b900386d/packages/captcha-solver/index.js#L33-L33)

Provider powering this solver.

Type: CaptchaSolverProvider

* * *

#### [createTask](https://github.com/transitive-bullshit/captcha-solver/blob/170214d0031b20cd05080088b16434b7b900386d/packages/captcha-solver/index.js#L44-L64)

Creates a new captcha solving task.

Type: `function (opts)`

-   `opts` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)** Options
    -   `opts.type` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Type of captcha to solve
    -   `opts.image` **([buffer](https://nodejs.org/api/buffer.html) \| [string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String))** Path, URL, or buffer of an image to process

* * *

#### [getTaskResult](https://github.com/transitive-bullshit/captcha-solver/blob/170214d0031b20cd05080088b16434b7b900386d/packages/captcha-solver/index.js#L76-L99)

Fetches the result of a previously created captcha solving task.

Type: `function (taskId, opts)`

-   `taskId` **[string](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)** Unique task identifier
-   `opts` **[object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)?** Options (optional, default `{}`)
    -   `opts.retries` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Number of retries to perform (optional, default `3`)
    -   `opts.timeout` **[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)** Max timeout to wait in ms before aborting (optional, default `30000`)

* * *

## Related

-   [puppeteer](https://github.com/GoogleChrome/puppeteer) - Headless Chrome Node API used under the hood.
-   [puppeteer-email](https://github.com/transitive-bullshit/puppeteer-email) - Email automation driven by headless chrome.
-   [sms-number-verifier](https://github.com/transitive-bullshit/sms-number-verifier) - Allows you to spoof SMS number verification.
-   [awesome-puppeteer](https://github.com/transitive-bullshit/awesome-puppeteer) - A curated list of awesome puppeteer resources.

## Disclaimer

Using this softare to violate the terms and conditions of any third-party service is strictly against the intent of this software. By using this software, you are acknowledging this fact and absolving the author or any potential liability or wrongdoing it may cause. This software is meant for testing and experimental purposes only, so please act responsibly.

## License

MIT © [Travis Fischer](https://github.com/transitive-bullshit)
