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

