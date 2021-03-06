<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo_text.svg" width="320" alt="Nest Logo" /></a>
</p>

[travis-image]: https://api.travis-ci.org/nestjs/nest.svg?branch=master
[travis-url]: https://travis-ci.org/nestjs/nest
[linux-image]: https://img.shields.io/travis/nestjs/nest/master.svg?label=linux
[linux-url]: https://travis-ci.org/nestjs/nest
  
  <p align="center">A progressive <a href="http://nodejs.org" target="blank">Node.js</a> framework for building efficient and scalable server-side applications, heavily inspired by <a href="https://angular.io" target="blank">Angular</a>.</p>
    <p align="center">
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/v/@nestjs/core.svg" alt="NPM Version" /></a>
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/l/@nestjs/core.svg" alt="Package License" /></a>
<a href="https://www.npmjs.com/~nestjscore"><img src="https://img.shields.io/npm/dm/@nestjs/core.svg" alt="NPM Downloads" /></a>
<a href="https://travis-ci.org/nestjs/nest"><img src="https://api.travis-ci.org/nestjs/nest.svg?branch=master" alt="Travis" /></a>
<a href="https://travis-ci.org/nestjs/nest"><img src="https://img.shields.io/travis/nestjs/nest/master.svg?label=linux" alt="Linux" /></a>
<a href="https://coveralls.io/github/nestjs/nest?branch=master"><img src="https://coveralls.io/repos/github/nestjs/nest/badge.svg?branch=master#5" alt="Coverage" /></a>
<a href="https://gitter.im/nestjs/nestjs?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=body_badge"><img src="https://badges.gitter.im/nestjs/nestjs.svg" alt="Gitter" /></a>
<a href="https://opencollective.com/nest#backer"><img src="https://opencollective.com/nest/backers/badge.svg" alt="Backers on Open Collective" /></a>
<a href="https://opencollective.com/nest#sponsor"><img src="https://opencollective.com/nest/sponsors/badge.svg" alt="Sponsors on Open Collective" /></a>
  <a href="https://paypal.me/kamilmysliwiec"><img src="https://img.shields.io/badge/Donate-PayPal-dc3d53.svg"/></a>
  <a href="https://twitter.com/nestframework"><img src="https://img.shields.io/twitter/follow/nestframework.svg?style=social&label=Follow"></a>
</p>
  <!--[![Backers on Open Collective](https://opencollective.com/nest/backers/badge.svg)](https://opencollective.com/nest#backer)
  [![Sponsors on Open Collective](https://opencollective.com/nest/sponsors/badge.svg)](https://opencollective.com/nest#sponsor)-->

## Description

[Nest](https://github.com/nestjs/nest) framework TypeScript starter repository.

## Installation

```bash
$ npm install
```

## Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Using the app


Go to localhost:4000 ([frontend](https://github.com/ccims/database-service/blob/dev/database-serviceui/README.md)) to customize the settings: Response type, response time, semantic correctness of response and simulated cpu utilization value.

With `localhost:3000`, one gets the status of the database service. This is again adjustable by toggling the Request Type Success checkbox and the response time of the response on localhost:4000.

With `localhost:3000/cpu/simulated`, one gets the simulated cpu utilization value of the database service.

With `localhost:3000/cpu`, the actual cpu utilization value of the database service on the vm is fetched.

With `localhost:3000/account-worth`, one gets a fixed account worth. 
(This method is used in conjunction with the chained request use case where the account service calls the price service which then makes a request to this endpoint to get the account worth)

With `localhost:3000/api` you can see all the Endpoints listed below, generated from the Swagger IO. 
The Swagger JSON file can be found at `localhost:3000/api-json`.

### Request types

There are different request types at different endpoints. The endpoint is specified after `localhost:3000/request-handler/[endpoint]`.
The semantic response type (correct/incorrect) can be adjusted in the UI of the database service at `localhost:4000`. A semantically incorrect response will either contain a simple string or a number in the case of GET requests and the request is rejected when a request is sent to the POST endpoint in the case of the incorrect response. The correct response will lead to a message denoting the success.

Endpoints:
[GET]:
- balance: semantically correct response: 31 - semantically incorrect response: "Jeff"
- customer-name: semantically correct response: "Jeff" - semantically incorrect response: 31

[POST]:
Here, we mainly compare the status codes.

- add-customer: semantically correct response: "Customer [post body] successfully added!" - semantically incorrect response is the rejection of the request


