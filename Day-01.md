# DOCKER -DAY-1

```bash
vim index.html
```
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Hello World - Nginx Docker</title>
    <style>
        h1{
            font-weight:lighter;
            font-family: Arial, Helvetica, sans-serif;
        }
    </style>
</head>
<body>
    
    <h1>
        Hello World
    </h1>

</body>
</html>
```
docker build -t simple-nginx .
docker run --rm -it -p 8080:80 simple-nginx
- --rm tells docker to remove the container once its stopped,
- -it is used to attach interactive TTY,
- -p 8080:80 is used to map the port 80 from the container to our computer port 8080,
- so, if we access localhost:8080 it means we are accessing the container.ip:80.
