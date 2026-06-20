# greetings
## Build Docker Image
docker build --no-cache -t my-spring-app:j25 .

## Run Docker Container
docker run -d -p 8080:8080 --name my-spring-container my-spring-app:j25

## Run Docker Container with Env Variables
docker run -p 8080:8080 \
  -e SPRING_PROFILES_ACTIVE=prod \
  -e SPRING_DATASOURCE_URL=jdbc:postgresql://host.docker.internal:5432/mydb \
  -e SPRING_DATASOURCE_USERNAME=myuser \
  -e SPRING_DATASOURCE_PASSWORD=mypassword \
  my-spring-app:j25
