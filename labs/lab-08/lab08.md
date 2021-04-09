# Lab 8 - Open Source Licensing
### email: faluyc@rpi,edu
### github account: TheCovenant
### discord handle: Kovenant (Kovenant#0067)

## Example 00

### Proof of Docker Installation: 

![whale](whale.png)

## Example 01



### Vim:

![Vim](vim.png)

### Cowsay:

![Cow](cowsay.png)

## Example 02

### Rocket Chat:

![Browser](rocket.png)


### Some container commands:

![Containers](commands.png)


## Example 3:

### Building the Docker Container:

![Build](dockerbuild.png)

###  browswer:

![Hello](hello.png)


## Example 4:

### Trying to run the app:

![first run](ex4.1.png)

### Docker file:

```
# Use node 10.15.3 LTS
FROM node:10.15.3
ENV LAST_UPDATED 20190325T175400

# Copy source code
COPY . /app

# Change working directory
WORKDIR /app

# Install dependencies
RUN npm install

# Fix up some of the issues
RUN npm audit fix

# Expose API port to the outside
EXPOSE 1337

# Launch application
CMD ["node","app.js"]
```

### Compose File:

```
version: '3'
services:
  mongo:
    image: mongo:4.0.7
    volumes:
      - mongo-data:/data/db
    expose:
      - "27017"
  app:
    build: .
    ports:
            - "1337:1337"
    links:
      - mongo
    depends_on:
      - mongo
    environment:
      - MONGO_URL=mongodb://mongo/messageApp
volumes:
  mongo-data:
```

### Server Running:

![Running](ex4.2.png)

### Chat Working:

![Chat](ex4.3.png)

