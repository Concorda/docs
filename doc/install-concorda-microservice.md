Back to [TOC](../Readme.md)

# Simple install

## Installing and running Concorda's Administration Dashboard

Clone github repository for [Concorda Dashboard](https://github.com/concorda/concorda-dashboard)

```
git clone git@github.com:concorda/concorda-dashboard.git
```

then

1. Run `npm install` to install all dependencies
2. Copy `config/sample.env` to `config/production.env` and add the right configuration in there.
3. In your `env` file set `EXTERNAL_API=false` and `EXTERNAL_CORE=true`
4. Set true what type you want to use for transport between client application and Concorda: mesh or tcp
5. Run `npm run build` to build the project.
6. Run `npm start:production` to create a deploy and server on port `3050` in production mode


## Installing and running Concorda microservice

Clone github repository for [Concorda Dashboard](https://github.com/concorda/concorda)

```
git clone git@github.com:concorda/concorda.git
```

then

1. Run `npm install` to install all dependencies
6. Run `npm run start` to run it


# Installing with Fuge

## Requirements

The basic tools are:

   * [Node.js 4](http://nodejs.org)
   * [Docker 1.8](http://docker.com)

Install these before getting started.

## Installing 

Clone github repository for [Concorda Fuge](https://github.com/concorda/concorda-fuge)

```
git clone git@github.com:concorda/concorda-fuge.git
```

This project is using Fuge to start the required deployment.

## How to use this code

```sh
$ npm install
```

to get the dependent Node.js modules.

## How to start

You can start demo system by using the [fuge](https://github.com/apparatus/fuge) commands.
from inside concorda-fuge folder

```sh
$ fuge shell system_concorda_microservice.yml
? fuge> start all
```

![Diagram](https://github.com/Concorda/docs/blob/master/img/concorda-microservice.jpeg)

IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.
3. Now you need to install and use ```concorda-client``` in your application as described [here](./using-concorda-plugin.md)