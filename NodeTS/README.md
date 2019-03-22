# Docker-NodeTS

Run app
---

### Creating docker image
This need to be created directly in folder of this project
```bash
docker build . --no-cache -t node-ts
```

### Alias node-docker machine
```bash
echo 'alias nodets-docker="docker run --rm --interactive --tty --volume \$PWD:/app -p 0.0.0.0:80:4000 --user \$(id -u):\$(id -g) node-ts"' >> ~/.bashrc
```

### Alias node-docker-cmd machine for running commands
```bash
echo 'alias nodets-docker-cmd="docker run --rm --interactive --tty --volume \$PWD:/app --user \$(id -u):\$(id -g) node-ts"' >> ~/.bashrc
```

### Prepare server
```bash
nodets-docker-cmd npm install
```

### Run server
```bash
nodets-docker npm start
```

### Check running in browser
```bash
http://0.0.0.0
```
