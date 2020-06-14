# Maven Spring Boot Docker Example
[![Build](https://github.com/simontunnat/maven-spring-boot-docker-example/workflows/CI/badge.svg)](https://github.com/simontunnat/maven-parent/actions?query=workflow%3ACI)
[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0)

This is an example for how to build a Spring Boot App with Maven and package it as a Docker container.

## Requirements
* Java Version 8 or later (the project is build against JDK 8, 11 and 14)

## Usage
### Run locally with Maven
Execute the following command:
```
mvn clean spring-boot:run
```

Then open in a browser:
```
http://localhost:8080
```

### Run locally with Docker
Execute the following commands:
```
mvn clean verify

docker load --input target/jib-image.tar

docker run --rm -p 8080:8080 docker.pkg.github.com/simontunnat/maven-spring-boot-docker-example/maven-spring-boot-docker-example
```

Then open in a browser:
```
http://localhost:8080
```

### Install to Docker Registry and pull from there
Execute the following commands:
```
mvn clean install

docker run --rm -p 8080:8080 docker.pkg.github.com/simontunnat/maven-spring-boot-docker-example/maven-spring-boot-docker-example
```

Then open in a browser:
```
http://localhost:8080
```

## Legal
Copyright 2020 Simon Tunnat

Licensed under the [Apache License](LICENSE), Version 2.0.