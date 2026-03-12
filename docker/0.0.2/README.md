# audio-dataset-converter 0.0.2 (based on code in repos)

## Build

```bash
docker build -t audio-dataset-converter:0.0.2 .
```

## Local

### Deploy

* Log into https://harbor.cms.waikato.ac.nz with user that has write access

  ```bash
  docker login -u USER harbor.cms.waikato.ac.nz
  ```

* Execute commands

  ```bash
  docker tag \
      audio-dataset-converter:0.0.2 \
      harbor.cms.waikato.ac.nz/public/tools/audio-dataset-converter:0.0.2
      
  docker push harbor.cms.waikato.ac.nz/public/tools/audio-dataset-converter:0.0.2
  ```

### Use

```bash
docker run --rm -u $(id -u):$(id -g) \
    -v /local/dir:/workspace \
    -it harbor.cms.waikato.ac.nz/public/tools/audio-dataset-converter:0.0.2
```

**NB:** Replace `/local/dir` with a local directory that you want to map inside the container. 
For the current directory, simply use `pwd`.


## Docker hub

### Deploy

* Log into docker hub as user `waikatodatamining`:

  ```bash
  docker login -u waikatodatamining
  ```

* Execute command:

  ```bash
  docker tag \
      audio-dataset-converter:0.0.2 \
      waikatodatamining/audio-dataset-converter:0.0.2
  
  docker push waikatodatamining/audio-dataset-converter:0.0.2
  ```

### Use

```bash
docker run --rm -u $(id -u):$(id -g) \
    -v /local/dir:/workspace \
    -it waikatodatamining/audio-dataset-converter:0.0.2
```

**NB:** 

* Replace `/local/dir` with a local directory that you want to map inside the container. 
* For the current directory, simply use `pwd`.
* You need to start the docker container with the `--net=host` option if you are using the host's Redis server.
