# The Docker Tutorial Notes

## Using a `Dockerfile`

Build our own container with a custom `Dockerfile`

```dockerfile=
# From Command is Followed by base image you want to build off of.
FROM node.js 

# Determine which directory we will be in (will be created if it is not there)
WORKDIR /home/server

RUN npm install -g json-server
COPY db.json /home/server/db.json
```
Tell docker to run json server: 
1. Entrypoint is the main command ran by the docker container - sole purpose not overwrtitten from host machine
2. CMD will run after the entrypoint command
