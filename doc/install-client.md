Back to [TOC](../Readme.md)

# Installing the client

The client is your application, that you want to be protected by Concorda.

In order to use Concorda some simple things needs to be done:

 * Run `npm install concorda-client --save` to install concorda-client in your project folder

Now you need to use concorda-client like this:
 
```

var Hapi = require('hapi')
var Bell = require('bell')
var Chairo = require('chairo')
var Cookie = require('hapi-auth-cookie')

const ConcordaClient = require('concorda-client')

// Options for our hapi plugins.
var opts = {
  server: {
    port: process.env.PORT || 3000
  }
}

// Log and end the process on err.
function endIfErr (err) {
  if (err) {
    console.error(err)
    process.exit(1)
  }
}

// Create our server.
var server = new Hapi.Server()
server.connection({port: opts.server.port})

// Declare our Hapi plugin list.
var plugins = [
  {register: Bell},
  {register: Cookie},
  {register: Chairo}
]

// Register our plugins.
server.register(plugins, function (err) {
  endIfErr(err)

  // add any required seneca plugin
  var seneca = server.seneca
  
  seneca.use(ConcordaClient, {....concorda client options - see bellow please})

  // now you can add all your HTTP services

  // Kick off the server.
  server.start(function (err) {
    endIfErr(err)

    server.seneca.log.info('Listening at: ', server.info.port)
  })
})
```

Of course you can organize your code in different files, above is just a simple example of using concorda-client. 

## Concorda client options

Concorda client has the following options:

 - ```appkey``` - unique key in the system, used internally to identify the application in the Concorda system.
 - ```mesh``` - JSON
    - ```active```: true | false (default false) - enable or disable the [mesh](https://github.com/rjrodger/seneca-mesh) transport support for communicating with Concorda application
    - all other mesh options (nothing required for default)
 - ```transport``` - JSON
    - ```active```: true | false (default false) - enable or disable the [seneca transport](https://github.com/senecajs/seneca-transport) support for communicating with Concorda application
    - ```type```:  (default 'tcp') type of transport
 - ```auth``` - JSON
    - ```restrict``` (default: '/api') - define restricted rest api - see [Seneca-auth](https://github.com/senecajs/seneca-auth) for details.
    - ```password``` - define the cookie password, should be at least 32 character long
    - other options as defined by [Seneca-auth](https://github.com/senecajs/seneca-auth)


##### Next options are required when using external auth providers like Google/Github/Twitter

 - ```concordaProtocol``` - protocol used by Concorda server  
 - ```concordaHost``` - host used by Concorda server
 - ```concordaPort``` - port used by Concorda server
 - ```protocol``` - protocol for current client application
 - ```host``` - host for current client application
 - ```port``` - port for current client application
      
      
## Demo Client example

You can take a look on the [Demo client](https://github.com/Concorda/concorda-client-demo) repository for an example of implementing the client.

IMPORTANT NOTES
===============

1. By default the following user is added to Concorda as part of initial setup: admin@concorda.com/concorda
2. It is very important that after you started Concorda for the first time to login and change administrator password and e-mail.