Back to [TOC](../Readme.md)

# Installing Concorda as a standalone server

Clone github repository for [Concorda Dashboard](https://github.com/concorda/concorda-dashboard)

```
git clone git@github.com:concorda/concorda-dashboard.git
```

then

1. Run `npm install` to install all dependencies
2. Copy `config/sample.env` to `config/production.env` or `config/development.env` and put the right configuration in there.
3. In your `env` file set `EXTERNAL_API=false` and `EXTERNAL_API=false`
4. Run `npm run build` to build the project.
4. Run `npm start:production` to create a deploy and server on port `3050` in production mode
	OR
	`npm run start:dev` to create a deploy and server on port `3050` in development mode

Also you can watch the files for changes and automatically rebuild the sources by running `npm run watch`
in a different terminal.

![Diagram](https://github.com/Concorda/docs/blob/master/img/monolith.jpeg)

IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.