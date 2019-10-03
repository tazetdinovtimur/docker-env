### Build

Build docker container and tag it:

```sh
$ cd docker-composer
$ docker build -t dkr-node .
```
### Run

Run the container and mount the volume:

```sh
$ docker run -it --rm -v /path/to/project:/app dkr-node
```
Install dependencies

```sh
$ npm install
$ npm run build
```