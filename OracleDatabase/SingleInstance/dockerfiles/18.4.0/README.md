# Modifications

A very simple modification to make the generated image contain a prebuilt configured database.

This makes the startup (substantially) faster, and a better candidate to be used in automated integration tests.

# Example commands

## Build image

```shell script
$ docker build . -t oracledb:18c-xe -f Dockerfile.xe
```

## Run image with an initialization script

```shell script
$ docker run -ti --rm \
    -p 1521:1521 \
    -v $(pwd)/assets/initialize_db.sql:/opt/oracle/scripts/startup/init.sql:ro \
    oracledb:18c-xe
```

## Change sys, system, PDBADMIN password in a running container

```shell script
$ docker exec -ti xxxxxx /setPassword.sh oracle
```

