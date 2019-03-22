# Docker-React

Run app
---

### Creating docker image
This need to be created directly in folder of this project
```bash
docker build . --no-cache -t react-cli
```

### Alias react-docker machine
```bash
echo 'alias react-docker="docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) -p 0.0.0.0:80:3000 react-cli"' >> ~/.bashrc
```

### Alias react-docker-cmd machine for running commands
```bash
echo 'alias react-docker-cmd="docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) react-cli"' >> ~/.bashrc
```

### Installing my-app
Command can be used in any folder, but will create project in subfolder of that location
Ex. if you are in folder my-app, application will be in my-app/my-app folder
```bash
react-docker-cmd create-react-app my-app
```

### Run server after installing my-app
Go to my-app folder and run the server
```bash
react-docker yarn start
```

### Check running my-app running in browser
```bash
http://0.0.0.0/
```

