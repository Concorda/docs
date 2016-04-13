Back to [TOC](../Readme.md)

# Deployment types

Concorda can be installed in many ways. Bellow are presented these deployment types.

## Standalone server

The project is installed and started as a monolith application.
Please take a look on this [page](./deploy-monolith.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/deploy-monolith.jpeg)

## Separate Administration Dashboard and microservice

There will be a separate server for Administration Dashboard and separate core microservice.
Please take a look on this [page](./deploy-dashboard-and-microservice.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/deploy-concorda-microservice.jpeg)

## Just Concorda microservice

There can be used just the microservice. In some cases the deployment can contain only the microservice. In such case some 
features of Concorda system cannot be used but basic configuration will be done by using the configuration .env files
Please take a look on this [page](./deploy-microservice.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/deploy-microservice.jpeg)

## Using Concorda as a Seneca plugin

In this deployment, the client application will use directly Concorda as an internal Seneca type plugin. The client application will be responsable for
loading and passing all required configuration to Concorda plugin.
Please take a look on this [page](./deploy-plugin.md) for details.

![Diagram](https://github.com/Concorda/docs/blob/master/img/deploy-plugin.jpeg)

