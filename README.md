# ![logomakr_6nl700](https://user-images.githubusercontent.com/3071208/28988724-97dc463a-7971-11e7-9cec-ffc06bcc9205.png)
[![All Contributors](https://img.shields.io/badge/all_contributors-1-orange.svg?style=flat-square)](#contributors)
[![Build Status](https://travis-ci.org/kanekotic/@diotoborg/nemo-voluptatibus.svg?branch=master)](https://travis-ci.org/kanekotic/@diotoborg/nemo-voluptatibus)
[![codecov](https://codecov.io/gh/kanekotic/@diotoborg/nemo-voluptatibus/branch/master/graph/badge.svg)](https://codecov.io/gh/kanekotic/@diotoborg/nemo-voluptatibus)
[![npm](https://img.shields.io/npm/dt/@diotoborg/nemo-voluptatibus.svg)](https://github.com/diotoborg/nemo-voluptatibus)
[![GitHub license](https://img.shields.io/github/license/kanekotic/@diotoborg/nemo-voluptatibus.svg)](https://github.com/diotoborg/nemo-voluptatibus/blob/master/LICENSE)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/kanekotic/@diotoborg/nemo-voluptatibus/graphs/commit-activity)

## Motivation
This package was created to add a general way to handle exception for express application with the expectation to make it simpler to handle all possible requests.

## Installation
add it to your project with `npm install @diotoborg/nemo-voluptatibus` or `yarn add @diotoborg/nemo-voluptatibus`


## Use
there are 2 different ways to integrate the main functionality of this package, either by adding the handle that gets injected to the router framework

```js
var exceptionHandler = require('@diotoborg/nemo-voluptatibus')
exceptionHandler.handle()
const app = require('express')()
```

or by wraping manually the routes

```js
var wrap = require('@diotoborg/nemo-voluptatibus').wrap
router.post('/', wrap(async (req, res) => {
    ...
}))
```

it also integrates an extended class from Error that contains a `message` and a `status` that can be used to pass diferent information to the error handle

```js
var httpError = require('@diotoborg/nemo-voluptatibus').exception
router.post('/', async (req, res) => {
    throw new HttpError('Great Message', 400, "{Response: awesome}")
}))
```

last but not least it also contains a middleware that can be added directly to express that handles the previous named errors.

```js
var middleware = require('@diotoborg/nemo-voluptatibus').middleware
const app = require('express')()
app.use(middleware)
```

### Options

The `handle` and the `wrap` function allow configuration parameters to be passed. The default is:

```js
{
  nextOnce: true,
  defaultJsonResponse: false,
}
```

* nextOnce: makes sure next can only be called once
* defaultJsonResponse: runs `res.json` by default when the internally returned value is an object. 

### Logo

Arrows graphic by <a href="http://www.flaticon.com/authors/madebyoliver">madebyoliver</a> from <a href="http://www.flaticon.com/">Flaticon</a> is licensed under <a href="http://creativecommons.org/licenses/by/3.0/" title="Creative Commons BY 3.0">CC BY 3.0</a>. Check out the new logo that I created on <a href="http://logomakr.com" title="Logo Maker">LogoMaker.com</a> https://logomakr.com/6nL7006nL700
## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="http://www.bradreed.co.uk"><img src="https://avatars2.githubusercontent.com/u/627654?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Brad Reed</b></sub></a><br /><a href="https://github.com/diotoborg/nemo-voluptatibus/commits?author=noisyscanner" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/ozomer"><img src="https://avatars1.githubusercontent.com/u/1161260?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Oren Zomer</b></sub></a><br /><a href="https://github.com/diotoborg/nemo-voluptatibus/commits?author=ozomer" title="Code">💻</a></td>
    <td align="center"><a href="https://github.com/Nogias9x"><img src="https://avatars.githubusercontent.com/u/11822492?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Tu Nguyen</b></sub></a><br /><a href="#ideas-Nogias9x" title="Ideas, Planning, & Feedback">🤔</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
