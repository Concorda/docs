Back to [TOC](../Readme.md)

# Simple install

## Installing only Concorda microservice

Note: Even if Concorda microservice is offering all required services for client authentication, in order to fully use the 
Concorda's features (includes user management, runtime configurations and others) you can use also Concorda Administration Dashboard, 
that can be installed and started as a separate application.

## Installing and running Concorda microservice

Clone github repository for [Concorda](https://github.com/concorda/concorda)

```sh
git clone git@github.com:concorda/concorda.git
```

then

1. Run `npm install` to install all dependencies 
2. Copy `config/sample.vars.env` to `config/production.env` and add there the right configuration.
3. **Set true what type you want to use for transport between client application and Concorda: mesh or tcp.**
   * Recommendation is to use TCP transport but also mesh or other types of transport (HTTP/HTPS) can be used.
   * Example:
   
```js
USE_MESH=false   
USE_TRANSPORT=true   
TRANSPORT_TYPE=tcp
```
   
4. Run `npm start` to start application and server on port `3070` (or whatever you specified in the `production.env` file)

## Concorda settings

When using without Concorda Dashboard, the only way to configure Concorda is by using the env configuration file.
On `config/production.env` file you will find these variables:

 * PUBLIC_REGISTER - allowed values "0"/"1" - disable/enable public user register. If public register is disabled ("0") then user register can be done only based on user invitation.
 * PASSWORD_POLICY - this will define the password policy to be used to enforce stronger user passwords.
    * requireLowercase - allowed values "0"/"1" - activate if lowercase characters are required in password
    * requireUppercase - allowed values "0"/"1" - activate if uppercase characters are required in password
    * requireNumeric - allowed values "0"/"1" - activate if numeric characters are required in password
    * minLength - numeric value - minimum length for user passwords.
 * AUTH_TYPE - this will define the allowed authentication types.
    * google - allowed values "0"/"1" - disable/enable google login
    * github - allowed values "0"/"1" - disable/enable github login
    * twitter - allowed values "0"/"1" - disable/enable twitter login
 * MAIL_TEMPLATE_FOLDER - absolute path to mail template folder. Example of mail templates can be found [here](https://github.com/Concorda/concorda/tree/master/lib/email-templates)
   

IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.
3. Now you need to install and use ```concorda-client``` in your application as described [here](./install-client.md)