docker version
# or
docker --version
# or
docker -v

docker build -t web-api .
docker images
docker run -d -p 32766:8080 hello-app:latest
docker ps

docker build -t hello-app:v1 .
docker tag hello-app:v1  e880613/hello-app:v1
docker push e880613/hello-app:v1
docker run -d -p 32766:8080 hello-app:v2

http://localhost:32766/

docker stop 79c669e62ff4
docker rm 79c669e62ff4

docker logs 79c669e62ff4


