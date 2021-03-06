# Purencool Httpd 


Purencool Httpd is an Application that runs in your browser locally.


## Getting Started

These instructions will cover usage information and for the docker container 

### Prerequisites

In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

### Usage

#### Container Parameters

Start service initially

```shell

 docker run  -p 80:8080 --mount type=bind,source="$(pwd)"/test/web,target=/var/www/html --name=purencool_httpd
```

Stop service 

```shell
 docker stop purencool_httpd
```

Start service again

```shell
docker start purencool_httpd
```

#### Environment Variables

* `VARIABLE_ONE` - A Description
* `ANOTHER_VAR` - More Description
* `YOU_GET_THE_IDEA` - And another

#### Volumes

* `/your/file/location` - File location

#### Useful File Locations

* `/some/special/script.sh` - List special scripts
  
* `/magic/dir` - And also directories

## Built With

* Docker version 19.03.13

## Find Us

* [GitHub](https://github.com/purencool/purencool-studio)
* [Purencool Digial](https://www.purencool.digital)
* [Docker image](https://hub.docker.com/repository/docker/purencool/purencool_httpd/general)

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. 

## Authors

* **Purencool** - *Initial work* - [Purencool Digital](https://purencool.digital)



## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE) file for details.

## Acknowledgments

* Purencool team


### Build
For this to build you will need to do the following
1. config.js needs to be installed
2. run `docker build -t "purencool_httpd:latest" .`


### Development

The below commands we use commonly in the development of this docker image

#### Docker build commands


```
docker images
```
Completely delete any reference of purencool_httpd locally

```
docker stop purencool_httpd && \
docker rm  purencool_httpd && \
docker rmi -f purencool_httpd
```

To rebuild and test purencool_httpd locally

```
docker build -t "purencool_httpd:latest" . && docker images && \ 
docker run  -p 80:8080 --mount type=bind,source="$(pwd)"/test/web,target=/var/www/html --name=purencool_httpd -d  -t purencool_httpd:latest  && \
docker exec -it purencool_httpd  /bin/sh
```





##### Stop all docker ps

```
 docker stop $(docker ps -aq)
```


##### Removed all images that in a halted state 


```
 docker rm $(docker ps -aq)
```

##### Removed all dangling images

```
docker rmi $(docker images --quiet --filter "dangling=true")
```
