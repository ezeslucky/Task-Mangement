

Namviek is an open-source project manager for small teams with low budget. It includes essential features for running your team.

----

## Who is this for ?

This project is a great fit for people with developer skills who are running a small team on a limited budget, similar to me. Read full the [post](https://dev.to/hudy9x/i-built-a-free-open-source-project-manager-that-helps-teams-keep-costs-under-15month-3pmk)

## What tech stack I use

- Next.js
- Node.js
- MongoDB
- Redis



### Run with docker

```
 cp .env.example .env.local
 yarn compose-build
 yarn compose-up
```

Why do I have `docker-compose.services.yml` file ? If you're a developer who want to contribute this app, but don't want to setup all services on the cloud, then this file will help you run all services (Redis, MongoDB, Minio) and you just have to install Nx and run the codebase

### Run without docker

```
git clone https://github.com/ezeslucky/Task-Mangement.git
```

Next, install packages and nx.

```
 yarn install
 yarn global add nx@latest 
```


## Start Redis server
Make sure that your Redis is running. Redis is used for caching data so you can not run the app without it. Try to ping it as follow.

``` 
 redis-cli
127.0.0.1:6379> ping
PONG
127.0.0.1:6379>
```
## Create MongoDB Atlas database
Sign in MongoDB Atlas and create your own database. Remember to select your nearst region and redirect to Database Access area to create an user that access to the above database.

## Configure .env
Create your own .env file by copying .env.example and rename it. Or you can also create an empty one and paste these required configs. Mine is .env

``` 
// .env
NEXT_PUBLIC_FE_GATEWAY=http://localhost:4200/
NEXT_PUBLIC_BE_GATEWAY=http://localhost:3333/
NEXT_PUBLIC_APP_NAME=Namviek Dev
MONGODB_URL=mongodb+srv://{user}:{pwd}@cluster0.weszq.mongodb.net/{dbName}?retryWrites=true&w=majority
JWT_SECRET_KEY=12981KJ1H23KJH
JWT_REFRESH_KEY=287kjshkjshdf
JWT_VERIFY_USER_LINK_TOKEN_EXPIRED=1h
JWT_TOKEN_EXPIRED=30m
JWT_REFRESH_EXPIRED=4h
REDIS_HOST=


  ```



## Generate prisma schema
At this moment .env is ready, you need to generate the schema and push it to database. Open terminal and run these commands.


```
 yarn generate // for window user
 yarn generate2 // for linux or mac user
 yarn prisma db push --schema=./packages/shared-models/src/prisma/schema.prisma
```

## Run it
Lastly, open your terminal again and run the app.
```
$ yarn frontend
$ yarn backend
```

Open the app now: http://localhost:4200



