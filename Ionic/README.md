# Docker-Ionic

Run app
---

### Creating docker image
This need to be created directly in folder of this project
```bash
docker build . --no-cache -t ionic
```

### Alias ionic-docker machine
```bash
echo 'alias ionic-docker="docker run --rm --interactive --tty --volume \$PWD:/app -p 0.0.0.0:80:8100 --user $(id -u):$(id -g) ionic"' >> ~/.bashrc
```

### Alias ionic-docker-cmd machine for running commands
```bash
echo 'alias ionic-docker-cmd="docker run --rm --interactive --tty --volume \$PWD:/app --user $(id -u):$(id -g) ionic"' >> ~/.bashrc
```

### Creating myApp
Command can be used in any folder, but will create project in subfolder of that location
Ex. if you are in folder my-app, application will be in my-project/my-project folder
```bash
ionic-docker-cmd ionic start myApp sidemenu
```

### Run server after installing my-project
Go to my-project folder and run the server
```bash
ionic-docker ionic serve
```

### Check running my-project running in browser
```bash
http://0.0.0.0/
```
