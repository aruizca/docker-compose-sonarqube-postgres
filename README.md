# docker-compose-sonarqube-postgres
Run SonarQube with a PostgreSQL database using Docker Compose

## Docker images and tags used
- [sonarqube:lts](https://hub.docker.com/_/sonarqube/)
- [postgres:9](https://hub.docker.com/_/postgres/)

## Usage
Use docker-compose to start the containers.

```
$ docker-compose up
```

Restart the containers (after plugin upgrade or install for example).

```
$ docker-compose restart sonarqube
```

Analyse a project:

```
mvn sonar:sonar \
  -Dsonar.host.url=http://localhost:9000 \
  -Dsonar.jdbc.url=jdbc:postgresql://$(boot2docker ip)/sonar
```  