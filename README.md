## Notes integration local development tool

This repository contains a docker-compose.yml file that will setup three containers.
1. A postgres database.
2. The notes-api server.
3. The notes-web application.

This repo has both notes-api and notes-website as sub-modules.

# Clone recursively
To run locally you must also have the code for each internal repository.  
To clone recursively, please run:
```
git clone --recurse-submodules git@github.com:OtmaroE/notes-development.git
```

# Commands.
1. To run all containers and attach to their output.
```
docker compose up
```

2. To start all containers without attaching to output.
```
docker compose up -d
```

# Environment variables.

Use the `env.example` file to create your own `.env` file. For out-of-the-box local development, just copy/paste existing example into an `.env` file.

# Seeding the back-end

The back-end doesn't automatically seed the base users and data to local testing.  
To run them run the following comand once the api container is runing and healthy:
```
docker exec notes-api npm run db:seed
```
