# DAP (Docker-Apache-PHP)

Simple replacement for XAMPP-WAMP-LAMP like development stacks for Docker environment.

## Building Image

On your terminal, change directory to `Dockerfile` file's folder then build it with;

```sh
docker build -t dap .
```

## Installed PHP extensions:

Container runs PHP 7.4 with these PHP extensions;

- Redis
- MongoDB
- MySQL
- PostgreSQL
- SQLite3
- Multibyte String (mbstring)
- Curl
- Bzip2
- Image Processing (GD and ImageMagick)
- BC Match
- XML (SimpleXML, DOM, etc..)
- Zip

## Connecting local folder to container

Main PHP application runs in `/var/www` folder. You can connect any local folder to main app folder like;

```sh
docker run -d -p 80:80 -v /your/local/app/path:/var/www --restart=always ozguncagri/dap
```

## Connecting apache log folder to local folder

```sh
docker run -d -p 80:80 \
-v /your/local/app/path:/var/www \
-v /your/local/log/path:/var/log/apache2 \
--restart=always ozguncagri/dap
```

**PS :** This image prepared for development purposes only. **Don't** use it in production or modify it for your production environment. **Redis**, **MongoDB**, **MySQL** and **PostgreSQL** are only PHP extensions. This image doesn't contain any of these servers...
