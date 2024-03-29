# Sentrysk Dashboard Dockerized
With this repo you can set up **Sentrysk Dasbord** with Docker.

This docker-compose file includes:
- [Sentrysk Backend](https://github.com/sentrysk/Sentrysk-Backend)
- [Sentrysk Frontend](https://github.com/sentrysk/Sentrysk-Frontend)
- MongoDB
- Load Balancer(Nginx)

# How to Run
First thing first, you need to pull the **[Sentrysk Backend](https://github.com/sentrysk/Sentrysk-Backend)** and **[Sentrysk Frontend](https://github.com/sentrysk/Sentrysk-Frontend)** projects to upper folder.

PS: Skip step 1 and 2 if you already download these repos.

- Step 1: Pull the Backend
```
git clone https://github.com/sentrysk/Sentrysk-Backend
```

- Step 2: Pull the Frontend
```
git clone https://github.com/sentrysk/Sentrysk-Frontend
```

- Step 3: Pull the Docker Compose File
```
git clone https://github.com/sentrysk/Sentrysk-Dashboard-Docker
```

- Step 4: Enter the **Sentrysk-Dashboard-Docker** folder
```
cd Sentrysk-Dashboard-Docker
```

- Step 5: Docker Up
```
docker-compose up
```

# Changing Backend Replica Count
If you'd like to change backend replica count you should change **deploy -> replicas** value.
```
  # Flask backend service
  flask-app:
    build:
      context: ../Sentrysk Backend/
    ports:
      - "5000"
    depends_on:
      - mongo-db
    deploy:
      replicas: 3
```
