Back to [TOC](../Readme.md)

# Deploy as a Seneca plugin with all internal functionality

Note: Even if Concorda microservice is offering all required services for client authentication, in order to fully use the 
Concorda's features (includes user management, runtime configurations and others) you can use also Concorda Administration Dashboard, 
that can be installed and started as a separate application.

## Installing and running Concorda as internal Seneca plugin

Install Concorda module in your application

```sh
npm install --save concorda
```

then

```javascript
const Concorda = require('concorda')

module.exports = function (options) {
  var seneca = this

  seneca
    .use(Concorda, {
    .....options.....
    })

  return {
    name: 'your-plugin'
  }
}

```


IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.
3. Now you need to install and use ```concorda-client``` in your application as described [here](./install-client.md)