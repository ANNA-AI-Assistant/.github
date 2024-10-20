# A.N.N.A project

## Introduction

A.N.N.A is a numeric life assistant like J.A.R.V.I.S (home automation, bank account, IT, etc.).

This software is built on NestJS and a lot of other open source project.

## Technologies

- Backend :
  - API : powered by NestJS, use JWT auth and store data via Queue for asynchronous writing on many features
  - Harmonizer : Orchestrator for cronned function, powered by Queue and API to register new cron, store his data in main BDD
  - SwarmBrain : Run long process about LLM multi-agent request, listen on Queue and publy result to Librarian
  - Gladys : Listen about building information and share them with other services on demand, listen on Queue and MQTT
  - Guideon : Listen on personnal and professionnal event and register them to BDD, store event as Knowledge and study recurency to manage user profil
  - Fmirnof : Collect and react to IT agent in different devices
  - Librarian : Agent to store and search about knowledge in library
  - Inspector : Agent to collect data and search when and how handle it
  - Vega : Agent specialized in engineering and software, use Swarmbrain to solve problem and work on project
- Database :
  - Main : Main database is powered by PgSQL, TimescaleDb and Postgis. It use UUID as ID
  - Library : Second PgSQL BDD used to store knowledge, use UUID as ID
  - ...
- Queue :
  - RabbitMQ powered for standard queue
  - MQTT for domotic
  - Use custom lib to integrate Queue as module in Nest
- Libraries :
  - CommonLib : Having every common modules/dependencies
  - AiWrapper : Structured AI usage, use Langchain and Ollama
  - Queue : Queue management over RabbitMQ (can be integrated with different drivers)
- AI :
  - Ollama : LLM for basic task
  - Exo : Clustering LLM for big workload (Research in progress)
  - StableDiffusion : Generating image (Planned)
  - ...

## TODO

- Finishing a functional app featuring:
  - Home automation.
  - Industrial automation.
  - IT pool management with servers, desktop/laptop/sbc computers.
  - IT Network management
  - IOT support
- Creating an images and compose for Podman to create a fully functional container structure for hosting.
