## Installation 

### First Steps

***Note:** You will need docker to run this application*

Clone the repository
```bash
git clone https://github.com/Vishal-Chdhry/parking-garage.git
```

Install the dependencies
```bash
npm install
```

Start the database
```bash
docker compose up dev-db -d
```

### Running the app

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

### Testing

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```
###*Learning System Design Right Now*
## Requirements
1. Eventual Consistency
2. High Availability
3. Fault Tolerance
4. Performance of upload- low SLAs
5. Low Latency between upload and user visibility
6. Low latency when distributed
7. __DAU:__ 10 Million
8. __Creators:__ 100K

## Conclusions
1. More reads than writes, *ratio is 1:100*

## Design
1. We will have 3 databases, Video database *(Amazon S3)*, metadata database *(MongoDB)*, userdata database *(PostgreSQL)*

## Endpoints
### POST `/upload`
**Params:** user_data, metadata, video *(max length = 7 sec)*