# Docker-Angular

Run app
---

### Creating docker image
This need to be created directly in folder of this project
```bash
docker build . --no-cache -t angular-cli
```

### Alias angular-docker machine
```bash
echo 'alias angular-docker="docker run --rm --interactive --tty --volume \$PWD:/app -p 0.0.0.0:80:4200 --user $(id -u):$(id -g) angular-cli"' >> ~/.bashrc
```

### Alias angular-docker-cmd machine for running commands
```bash
echo 'alias angular-docker-cmd="docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) angular-cli"' >> ~/.bashrc
```

### Installing my-app
Command can be used in any folder, but will create project in subfolder of that location
Ex. if you are in folder my-app, application will be in my-project/my-project folder
```bash
angular-docker ng new my-project
```

### Run server after installing my-project
Go to my-project folder and run the server
```bash
angular-docker-cmd ng serve --host 0.0.0.0 --port 4200 --disable-host-check
```

### Check running my-project running in browser
```bash
http://0.0.0.0/
```

### Run unit tests
```bash
angular-docker-cmd ng test
```

### Run end-to-end tests
```bash
angular-docker-cmd ng e2e
```
