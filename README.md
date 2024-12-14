![App shot](https://github.com/hudy9x/namviek/assets/95471659/00cab20a-747a-4cf5-8f5e-105f314f7e2f)

Namviek is an open-source project manager for small teams with low budget. It includes essential features for running your team.

----

## Who is this for ?

This project is a great fit for people with developer skills who are running a small team on a limited budget, similar to me. Read full the [post](https://dev.to/hudy9x/i-built-a-free-open-source-project-manager-that-helps-teams-keep-costs-under-15month-3pmk)

## What tech stack I use

- Next.js
- Node.js
- MongoDB
- Redis

## What features are packed in ?

As mentioned before, this app includes some essential features for a small team such as:

![Features](https://github.com/hudy9x/namviek/assets/95471659/28b1d157-e765-49ab-b7fd-0f3c441661ad)

## How to use it.

### Run with docker

```
$ cp .env.example .env.local
$ yarn compose-build
$ yarn compose-up
```

Why do I have `docker-compose.services.yml` file ? If you're a developer who want to contribute this app, but don't want to setup all services on the cloud, then this file will help you run all services (Redis, MongoDB, Minio) and you just have to install Nx and run the codebase

### Run without docker

Additionally, check out [the setup guide](https://www.namviek.com/#download). If you encounter any errors during the setup process, you can refer to the full guide [here](https://docs.namviek.com/doc/installation).






