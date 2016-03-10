Back to [TOC](../Readme.md)

## Requirements

The basic tools are:

   * [Node.js 4](http://nodejs.org)
   * [Docker 1.8](http://docker.com)

Install these before getting started.

# Installing separate static files and Rest API servers

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

1. Run `npm install` to install all dependencies.
2. Copy `config/sample.env` to `production.env` and put the right configuration in there.
3. In your `env` file set `EXTERNAL_API=true` and `EXTERNAL_CORE=false`
4. Run `npm run build` to build the project.

## How to start

You can start demo system by using the [fuge](https://github.com/apparatus/fuge) commands.
from inside concorda-fuge folder

```sh
$ fuge shell system.yml
? fuge> start all
```

![Diagram](https://github.com/Concorda/docs/blob/master/img/static-rest.jpeg)

IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.