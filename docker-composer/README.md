### Build

Build docker container and tag it:

```sh
$ cd docker-composer
$ docker build -t dkr-composer .
```
### Run

Run the container and mount the volume:

```sh
$ docker run -it --rm -v /path/to/your/project:/app dkr-composer
```
Install dependencies

```sh
app# composer install
```
Exit container

```sh
app# exit
```