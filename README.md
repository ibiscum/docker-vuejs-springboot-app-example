# docker-vuejs-springboot-app-example
Simple application with vue js spring boot and docker (docker-compose).

Install JDK

       # Add Adoptium Temurin official GPG key:
       sudo apt-get update
       sudo apt-get install ca-certificates curl
       sudo install -m 0755 -d /etc/apt/keyrings
       sudo curl -fsSL https://packages.adoptium.net/artifactory/api/gpg/key/public -o /etc/apt/keyrings/adoptium.asc
       sudo chmod a+r /etc/apt/keyrings/adoptium.asc
       echo "deb [signed-by=/etc/apt/keyrings/adoptium.asc] https://packages.adoptium.net/artifactory/deb $(awk -F= '/^VERSION_CODENAME/{print $2}' /etc/os-release) main" | sudo tee /etc/apt/sources.list.d/adoptium.list

       sudo apt-get update
       sudo apt-get install temurin-17-jdk

To run the app just run:
- docker-compose build:
  - Generate backend image. docker-compose file will execute the backend docker file. I used a multi-stage docker image. Indeed spring boot app jar file will be built in first docker image and runned in second docker image.
  - generate front end image. docker-compose file will execute front end docker file and built font end image
  - docker-compose up:
       - postgres docker image will be donwloded from docker hub. postgres db container will be built.
       - back end container will be built.
       - front end container will be built.
