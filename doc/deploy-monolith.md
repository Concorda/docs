Back to [TOC](../Readme.md)

# Deploying Concorda as a standalone server

Clone github repository for [Concorda Dashboard](https://github.com/concorda/concorda-dashboard)

```sh
git clone git@github.com:concorda/concorda-dashboard.git
```

then

1. Run `npm install` to install all dependencies
2. Copy `config/sample.vars.env` to `config/production.env` and add there the right configuration.
3. In your `condif/production.env` file leave 
   * `EXTERNAL_API=false` - this controls if the services will be exposed using a different Hapi Server instance.
   * `EXTERNAL_CORE=false` - this controls if the core implementation of Concorda will be running as a separate microservice.
4. Set true what type you want to use for transport between client application and Concorda: mesh or tcp.
   * Recommendation is to use TCP transport but also mesh or other types of transport (HTTP/HTPS) can be used.
   * Example:
  
```sh
USE_MESH=false   
USE_TRANSPORT=true   
TRANSPORT_TYPE=tcp
```

5. Run `npm run build` to build the project.
6. Run `npm start` to start application and server on port `3050` (or whatever you specified in the `production.env` file)

Also you can watch the files for changes and automatically rebuild the sources by running `npm run watch`
in a different terminal.

![Diagram](https://github.com/Concorda/docs/blob/master/img/monolith.jpeg)

IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.