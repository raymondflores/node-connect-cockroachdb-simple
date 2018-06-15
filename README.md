# Connect PG Simple

A simple, minimal CockroachDB session store for Express/Connect

[![Build Status](https://travis-ci.org/voxpelli/node-connect-pg-simple.svg?branch=master)](https://travis-ci.org/voxpelli/node-connect-pg-simple)
[![Coverage Status](https://coveralls.io/repos/voxpelli/node-connect-pg-simple/badge.svg)](https://coveralls.io/r/voxpelli/node-connect-pg-simple)
[![dependencies Status](https://david-dm.org/voxpelli/node-connect-pg-simple/status.svg)](https://david-dm.org/voxpelli/node-connect-pg-simple)
[![Known Vulnerabilities](https://snyk.io/test/github/voxpelli/node-connect-pg-simple/badge.svg?targetFile=package.json)](https://snyk.io/test/github/voxpelli/node-connect-pg-simple?targetFile=package.json)
[![js-semistandard-style](https://img.shields.io/badge/code%20style-semistandard-brightgreen.svg?style=flat)](https://github.com/Flet/semistandard)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fvoxpelli%2Fnode-connect-pg-simple.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fvoxpelli%2Fnode-connect-pg-simple?ref=badge_shield)

## Installation

```bash
npm install connect-cockroachdb-simple
```

Once npm installed the module, you need to create the **session** table in your database. For that you can use the [table.sql](table.sql) file provided with the module:

## Usage

Examples are based on Express 4.

Simple example:

```javascript
var session = require('express-session');
var crdbSession = require('connect-cockroachdb-simple')(session);
var pg = require('pg');

app.use(session({
  store: new crdbSession({
    pg: pg,
    conString: YOUR_CONNECTION_STRING
  }),
  secret: process.env.FOO_COOKIE_SECRET,
  resave: false,
  cookie: { maxAge: 30 * 24 * 60 * 60 * 1000 } // 30 days
}));
```

## Advanced options
View original fork [here](http://https://github.com/voxpelli/node-connect-pg-simple "here") for advanced configuration.


## License
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fvoxpelli%2Fnode-connect-pg-simple.svg?type=large)](https://app.fossa.io/projects/git%2Bgithub.com%2Fvoxpelli%2Fnode-connect-pg-simple?ref=badge_large)