### Build

Build docker container and tag it:

```sh
$ cd docker-node
$ docker build -t dkr-node .
```
### Run

Run the container and mount the volume:

```sh
$ docker run -it --rm -p 8080:8080 -v /path/to/project:/app dkr-node
```
Install dependencies

```sh
app# npm install
app# npm run build
```
Exit container

```sh
app# exit
```