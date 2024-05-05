# @odczynflnpm/cum-quam-eligendi

[![build status](https://img.shields.io/github/actions/workflow/status/bergos/@odczynflnpm/cum-quam-eligendi/test.yaml?branch=master)](https://github.com/odczynflnpm/cum-quam-eligendi/actions/workflows/test.yaml)
[![npm version](https://img.shields.io/npm/v/@odczynflnpm/cum-quam-eligendi.svg)](https://www.npmjs.com/package/@odczynflnpm/cum-quam-eligendi)

A protocol handler wrapper for fetch.

## Usage

`@odczynflnpm/cum-quam-eligendi` doesn't contain any fetch implementations.
A map of protocol to implementation must be given to the constructor.
This example shows how to create a fetch for file, http and https URLs:

```javascript
import fileFetch from 'file-fetch'
import httpFetch from 'nodeify-fetch'
import protoFetch from '@odczynflnpm/cum-quam-eligendi'

const fetch = protoFetch({
  [null]: fileFetch,
  file: fileFetch,
  http: httpFetch,
  https: httpFetch
})

const res = await fetch(`file://${process.cwd()}/package.json`)
``` 
