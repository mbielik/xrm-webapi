# xrm-webapi
|Build|Chat|NPM|Semantic-Release|
|-----|----|---|----------------|
|[![Build Status](https://img.shields.io/travis/rust-lang/rust/master.svg?style=flat-square)](https://travis-ci.org/derekfinlinson/xrm-webapi)|[![Gitter](https://img.shields.io/gitter/room/nwjs/nw.js.svg?style=flat-square)](https://gitter.im/xrm-webapi/Lobby)|[![npm](https://img.shields.io/npm/v/xrm-webapi.svg?style=flat-square)](https://www.npmjs.com/package/xrm-webapi)|[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg?style=flat-square)](https://github.com/semantic-release/semantic-release)|

A Dynamics 365 Web Api TypeScript module for use in web resources or external web apps in the browser or node.

All requests return Promises. To support Internet Explorer, be sure to include a promise polyfill when deploying to CRM.

*Requires Dynamics CRM 2016 Online/On-Prem or later*

### Installation

##### Node

```
npm install --save-dev xrm-webapi
```
### Usage

Import the module into your TypeScript files

```typescript
import { Guid, retrieve, WebApiConfig } from "xrm-webapi";

const config = new WebApiConfig("8.2");

const account = await retrieve(config, "accounts", new Guid(""), "$select=name");

console.log(account.name);
```

As of v5, the WebApi class has been replaced by individual functions instead of the WebApi class. This allows for importing individual functions instead of the entire library to take advantage of tree shaking to should reduce bundle size. I recommend using [Babel](https://babeljs.io/) in
your builds to compile your scripts to browser compliant JavaScript. Feel free to use [d365-cli](https://github.com/derekfinlinson/d365-cli)
which sets up a ready to use web resources project.

#### Supported methods
* Retrieve
* Retrieve multiple (multiple pages)
* Retrieve multiple with Fetch XML
* Create
* Create with returned data
* Update
* Update with returned data
* Update single property
* Delete
* Delete single property
* Associate
* Disassociate
* Web API Functions
* Web API Actions
* Batch operations
* Impersonation

#### Samples
See [xrm-webapi-samples.ts](samples/xrm-webapi-samples.ts) for examples

### Useful Links

[Web API Reference](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/developer/webapi/perform-operations-web-api)
