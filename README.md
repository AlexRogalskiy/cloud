tuyapi/cloud
==============

[![forthebadge](https://forthebadge.com/images/badges/made-with-javascript.svg)](https://forthebadge.com)

A NodeJS wrapper for Tuya's [cloud API](https://docs.tuya.com/en/cloudapi/cloudAPI/index.html).

## Installation
`npm i @tuyapi/cloud`

## Usage
```javascript
const Cloud = require('@tuyapi/cloud');

let api = new Cloud({key: 'your-api-key', secret: 'your-api-secret'});

api.register({email: 'example@example.com', password: 'example-password'}).then(async sid => {
  let token = await api.request({action: 'tuya.m.device.token.create', data: {'timeZone': '-05:00'}});

  console.log(token) // => { secret: '0000', token: '01010101' }
});
```

## Development
1. Run `npm i -D`.
2. Add a file called `keys.json` with the contents
```javascript
{
  "key": "your-api-key",
  "secret": "your-api-secret"
}
```
3. Create a file called `dev.js` as a playground. Since `dev.js` is in `.gitignore`, it won't be committed.
4. To run tests, run `npm test`.
