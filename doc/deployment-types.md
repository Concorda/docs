Back to [TOC](../Readme.md)

# Deployment types

Concorda can be installed in many types. Bellow are presented these deployment types.

## Standalone server

The project is installed and is starting as a monolith, no additional micro-services necessary.
Please take a look on this [page](./install-monolith.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/monolith.jpeg)

## Separate Administration Dashboard and microservice

There will be a separate server for Administration Dashboard and separate core microservice.
Please take a look on this [page](./install-dashboard-and-microservice.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/concorda-microservice.jpeg)

## Just Concorda microservice

There can be used just the microservice. In some cases the deployment can contain only the microservice. In such case some 
features of Concorda system cannot be used but basic configuration will be done by using the configuration .env files
Please take a look on this [page](./install-microservice.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/microservice.jpeg)

