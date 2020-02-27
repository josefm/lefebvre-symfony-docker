# Install

## 1. Add dev.lefebvre.es to hosts file

```
127.0.0.1 dev.lefebvre.es
```

## 2.Install dependencies via composer

```
composer install
```

## 3. Create .env.local 

Create file ```.env.local``` in root folder with the following contents:

```
DATABASE_URL=mysql://root:root@db:3306/lefebvre?serverVersion=5.7
```

## 4. Build docker containers

Use the following commands:

```
docker-compose up -d --build
```

You can list the running containers using:

```
docker ps
```

Or you can also access to a container using:

```
docker exec -it _container_name bash
```

## 5. Access project

Open *http://dev.lefebvre.es/* in your browser :) 

