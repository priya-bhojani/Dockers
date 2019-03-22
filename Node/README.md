# Docker-Node

Run app
---

### Creating docker image
This need to be created directly in folder of this project
```bash
docker build . --no-cache -t node-js
```

### Alias node-docker machine
```bash
echo 'alias node-docker="docker run --rm --interactive --tty --volume \$PWD:/app -p 0.0.0.0:80:4000 --user $(id -u):$(id -g) node-js"' >> ~/.bashrc
```

### Alias node-docker-cmd machine for running commands
```bash
echo 'alias node-docker-cmd="docker run --rm --interactive --tty --volume $PWD:/app --user $(id -u):$(id -g) node-js"' >> ~/.bashrc
```

### Prepare server
```bash
node-docker-cmd npm install
```

### Run server
```bash
node-docker npm start
```

### Check running in browser
```bash
http://0.0.0.0
```
