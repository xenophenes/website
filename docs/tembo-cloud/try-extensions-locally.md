---
sidebar_position: 3
tags:
  - local
---

# Try extensions locally

This guide is for running a Postgres container locally that supports installing extensions with Trunk.

## Start Postgres using Docker

- You can start a Postgres container locally like this
```
docker run -d -it --name local-tembo -p 5432:5432 --rm quay.io/tembo/tembo-local
```
- The above image includes common system dependencies for extensions listed in [Trunk](https://pgt.dev). Some extensions have very large dependencies, and these are not included.

## Install extensions with Trunk

- Browse [Trunk](https://pgt.dev) to find interesting extensions
- Get a shell connection into your Postgres container
```
docker exec -it local-tembo /bin/bash
```

- Trunk install an extension
```
trunk install pgmq
```

## Enabling extensions

- Connect to Postgres. This works from inside or outside the Postgres container.
```
psql postgres://postgres:postgres@localhost:5432
```
- Enable an extension
```
CREATE EXTENSION pgmq CASCADE;
```
- List enabled extensions
```
\dx
```