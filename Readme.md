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

## 6. Develop project in container using docker-sync

1. Install docker-sync utility

*http://docker-sync.io/*

2. Run docker-sync on the root folder of the project:

```
docker-sync
```

3. Rebuild the containers:

```
docker-compose up -d --build
```

4. Access the php container and run:

```
composer install
```

or whatever commands you need. 

5. Open *http://dev.lefebvre.es/* in your browser :) 

6. Using Visual Studio Code install the followgin extensions:

*https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack*

7. Reopen the project in Visual Studio Code
