# 🐴 nginx-gunicorn-flask-server

## Description 



## Build Project 

  docker-compose up --build
  echo "server is now up on 8080:8080"

## docker-compose.yml

  version: "3"
  services:
    server:
      build: ./server
      container_name: flask
      restart: always
      expose:
        - 5000
    nginx:
      build: ./nginx
      container_name: nginx
      restart: always
      ports:
        - "8080:8080"
