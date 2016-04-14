Back to [TOC](../Readme.md)

# Deploy as a Seneca plugin

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
        appkey: 'concorda',
        auth: {
            restrict: '/api',
            password: process.env.COOKIE_PASSWORD || 'some long password'
        }    
    })

  return {
    name: 'your-plugin'
  }
}

```


## Concorda settings

When using it as a Seneca plugin some options should be passed to control various features of Concorda.

 * `appkey` - the application key - leave it with 'concorda' as this application is create by default in the DB. If you want another application key, plate create another application and set corresponding appkey here.
 * `publicRegister` - allowed values "0"/"1" - disable/enable public user register. If public register is disabled ("0") then user register can be done only based on user invitation.
 * `passwordPolicy` - this will define the password policy to be used to enforce stronger user passwords.
    * `requireLowercase` - allowed values "0"/"1" - activate if lowercase characters are required in password
    * `requireUppercase` - allowed values "0"/"1" - activate if uppercase characters are required in password
    * `requireNumeric` - allowed values "0"/"1" - activate if numeric characters are required in password
    * `minLength` - numeric value - minimum length for user passwords.
 * `authType` - this will define the allowed authentication types.
    * `google` - allowed values "0"/"1" - disable/enable google login
    * `github` - allowed values "0"/"1" - disable/enable github login
    * `twitter` - allowed values "0"/"1" - disable/enable twitter login
 * `emailTemplateFolder` - absolute path to mail template folder. Example of mail templates can be found [here](https://github.com/Concorda/concorda/tree/master/lib/email-templates)
   
An example of default settings used internally be Concorda is:

```json
{
  "publicRegister": "1",
  "authType": {
    "google": "0",
    "github": "0",
    "twitter": "0"
  },
  "configured": true,
  "passwordPolicy": {
    "requireLowercase": "0",
    "requireNumeric": "0",
    "requireUppercase": "0",
    "minLength": 6
  },
  "emailTemplateFolder": "/home/malex/workspace/nearForm/concorda/concorda/lib/email-templates/"
}
```


IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.

## Demo

A demo project that is using the Concorda as [plugin](https://github.com/Concorda/concorda-client-demo/blob/master/start_plugin.js) can be found [here](https://github.com/Concorda/concorda-client-demo).
