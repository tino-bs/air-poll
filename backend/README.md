<img src="https://nestjs.com/img/logo_text.svg" align="right" width="200" alt="Nest Logo" />

# Backend
> powered by [Nest](https://github.com/nestjs/nest)

### Makefile
In order to use the comfy `make` commands you should have the
[Make Automation Tool](https://www.gnu.org/software/make/manual/make.html) installed,
but it is not absolutely necessary to get the work done.  
*You can check by running `make -v` or `gmake -v` - each is equally efficient from v3 or later*

#### Makefile support for your IDE
[Jetbrains](https://plugins.jetbrains.com/plugin/9333-makefile-support) or
[VS Code](https://marketplace.visualstudio.com/items?itemName=carlos-algms.make-task-provider)

## Setup
Make sure to have [yarn](https://classic.yarnpkg.com/en) (or later)
and [Docker](https://docs.docker.com/get-docker/) (including *docker compose*) installed.

### Make setup
```bash
make setup
```

### Or step by step
#### 1. Environment variables
copy the file `.env.example` to `.env`

#### 2. Install Dependencies
```bash
yarn
```

### Optional: Local environment overrides
Copy the file `.env.local.example` to `.env.local` and change your desired variables in the copied file.

## Run The App
### Make start
```bash
make start-standalone
```

### Or step by step
#### 1. Start docker containers for db
```bash
docker-compose up
```

#### 2. Start node app
```bash
# development mode
yarn start:dev

# production mode
yarn start:prod
```

## Tests
### Make tests
```bash
make tests
```

### Or step by step
#### 1. Unit tests
```bash
yarn test:unit
```

#### 2. End-to-end tests
```bash
docker-compose up -d
yarn test:e2e
docker-compose stop
```

## Postgres DB

### Local connection to the database
#### 1. Start docker container, if it is not already running
```bash
docker-compose up -d
```

#### 2.a Connection via pgAdmin
* visit http://localhost:8080
* enter `{PGADMIN_DEFAULT_EMAIL}` and `{PGADMIN_DEFAULT_PASSWORD}`

*See the [pgAdmin docs](https://www.pgadmin.org) for further information*

#### 2.b Connection via bash
```bash
docker-compose run postgres bash
```
```bash
psql --host=postgres --username={POSTGRES_USER} --dbname={POSTGRES_DB}
```

enter `{POSTGRES_PASSWORD}`
  
*For detailed explanation on how things work, run `help`
or check out the [Postgres docs](https://www.postgresql.org/docs).*

run `exit` to exit

## Admin
> powered by [AdminBro](https://softwarebrothers.github.io/admin-bro-dev)

*visit http://localhost:4000/admin*

## Nest
For detailed explanation on how things work, run 
```bash
yarn help:me
```
or check out the [Nest docs](https://docs.nestjs.com).
