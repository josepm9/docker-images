# Modifications

A very simple modification to make the generated image contain a prebuilt configured database.

This makes the startup (substantially) faster, and a better candidate to be used in automated integration tests.

# Example commands

## Build image

```shell script
$ docker build . -t oracledb:12c-ee -f Dockerfile.ee
```

```shell script
$ docker build . -t oracledb:12c-se2 -f Dockerfile.se2
```

## Run image

```shell script
$ docker run --rm -ti -p 1521:1521 oracledb:12c-ee
```

```shell script
$ docker run --rm -ti -p 1521:1521 oracledb:12c-se2
```    

## Change sys, system, PDBADMIN password

```shell script
$ docker exec -ti xxxxxx /setPassword.sh oracle
```    
