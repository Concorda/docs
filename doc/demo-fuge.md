Back to [TOC](../Readme.md)

# Demo system with fuge

## Requirements

The basic tools are:

   * [Node.js 4](http://nodejs.org)
   * [Docker 1.8](http://docker.com)

Install these before getting started.

## How to use this code

You can clone these branches directly - for example:

```sh
$ git clone https://github.com/vidi-insights/vidi-dashboard concorda-client
$ git clone https://github.com/nearform/concorda
$ git clone https://github.com/nearform/concorda-fuge
```

To save your own work, it is better to first fork the repository on github.com, and then clone them locally

In each repository, you always need to

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

There are some examplee yml files that defines the demo systems, such as:
 - system_monolith_mesh.yml - consist in:
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