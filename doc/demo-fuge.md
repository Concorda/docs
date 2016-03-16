Back to [TOC](../Readme.md)

# Demo system with [Fuge](https://github.com/apparatus/fuge)

## Requirements

The basic tools are:

   * [Node.js 4](http://nodejs.org)
   * [Docker 1.8](http://docker.com)

Install these before getting started.

## How to use this code

You can clone these branches directly - for example:

```sh
$ git clone https://github.com/concorda/concorda-fuge
```

You need to install all dependencies:

```sh
$ npm install
```

to get the dependent Node.js modules.
This must be done each time a branch is changed for each micro-service.

## How to start

You can start demo system by using the [fuge](https://github.com/apparatus/fuge) commands.
from inside concorda-fuge folder

```sh
$ fuge shell system.yml
? fuge> start all
```

## Demo fuge examples

There are some examples .yml files that defines the demo systems, such as:
 - system_monolith_mesh.yml:
     - Concorda Dashboard deployed as a monolith application
     - Client demo application
     - Mesh base
     - Postgres DB_
     - For Client<->Concorda Dashboard communication there is used [seneca-mesh](https://github.com/rjrodger/seneca-mesh)
 - system_monolith_tcp.yml - consist in:
     - Concorda Dashboard deployed as a monolith application
     - Client demo application
     - Postgres DB_
     - For Client<->Concorda Dashboard communication there is used [seneca-transport](https://github.com/senecajs/seneca-transport)
 - system_concorda_microservice.yml - consist in:
     - Concorda Dashboard
     - Concorda as microservice
     - Client demo application
     - Postgres DB_
     - For Client<->Concorda communication there is used [seneca-mesh](https://github.com/rjrodger/seneca-mesh)    
    

**Notes:**

 - For using curl command to see results please see [concorda-client-demo](https://github.com/concorda/concorda-client-demo)
 - [Vidi Dashboard](https://github.com/vidi-insights/vidi-dashboard) can be used instead of [concorda-client-demo](https://github.com/concorda/concorda-client-demo). Vidi project has also a React UI that can be used as demo.
    