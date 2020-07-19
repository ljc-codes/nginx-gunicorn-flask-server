# 🐴 nginx-gunicorn-flask-server

## Description 
This is a lightweight startercode for a gunicorn server, hosting a flask app. The app is served through a reverse proxy nginx server. Servers are docker-composed into one container.

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
