# Docker-PHP

Run app
---

### Creating docker image
This need to be created directly in folder of this project
```bash
docker build . --no-cache -t php-fpm
```

### Alias php-docker machine
```bash
echo 'alias php-docker="docker run --rm --interactive --tty --volume $PWD:/usr/src/app --user $(id -u):$(id -g) -p 0.0.0.0:80:80 php-fpm"' >> ~/.bashrc
```

### Alias php-docker-cmd machine for running commands
```bash
echo 'alias php-docker-cmd="docker run --rm --interactive --tty --volume $PWD:/usr/src/app --volume $PWD/.composer:/.composer --user $(id -u):$(id -g) php-fpm"' >> ~/.bashrc
```

### Prepare server
```bash
php-docker-cmd composer create-project symfony/skeleton my_project
```

### Run server
```bash
php-docker
```

### Check running in browser
```bash
http://0.0.0.0:80
```
