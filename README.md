# danger-plugin-no-console

[![Build Status](https://travis-ci.org/rizalibnu/danger-plugin-no-console.svg?branch=master)](https://travis-ci.org/rizalibnu/danger-plugin-no-console)
[![npm version](https://badge.fury.io/js/danger-plugin-no-console.svg)](https://badge.fury.io/js/danger-plugin-no-console)
[![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

> Danger plugin to prevent merging code that still has `console.log`s inside it.

## Usage

Install:

```sh
yarn add danger-plugin-no-console-ext --dev
```

At a glance:

```js
// dangerfile.js
import { schedule } from 'danger'
import noConsole from 'danger-plugin-no-console-ext'

// Note: You need to use schedule()
schedule(noConsole())
```

### Output example

<table>
  <thead>
    <tr>
      <th width="50"></th>
      <th width="100%" data-danger-table="true">Fails</th>
    </tr>
  </thead>
  <tbody><tr>
      <td>⛔️</td>
      <td>

  1 console statement(s) left in src/add.js.
  </td>
    </tr>
  </tbody>
</table>

### Options

#### `whitelist`

You can specify a whitelist of console properties to let pass. This is useful to e.g. let errors be logged, like so:

```js
// dangerfile.js
import noConsole from 'danger-plugin-no-console'

// Any file that contains console.log or console.info will fail,
// but files can contain console.error and console.warn
schedule(noConsole({ whitelist: ['error', 'warn'] }))
```

## Changelog

See the GitHub [release history](https://github.com/rizalibnu/danger-plugin-no-console/releases).

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).
