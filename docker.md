## Build docker image

These are some handy docker commands (use of sudo is not required if you have appropriate permissions):

## Build a docker image:
```
$ cd /path/to/Dockerfile
$ [sudo] docker build .
```

View running processes
```
$ [sudo] docker ps
```

View all processes

```
$ [sudo] docker ps -a
```

Run an image in a new container daemonized

```
$ [sudo] docker run -d <image_name>
```

Run an image in interactive mode with the command `/bin/bash`

```
$ [sudo] docker run -i -t <image_name> /bin/bash
```

Run an image in interactive mode with the command `/bin/bash` and link the ports.

```
$ [sudo] docker run -i -t --link <docker_container_name>:<docker_container_alias> <image_name> /bin/bash
```

Run an image with an ENTRYPOINT command in interactive mode with the command `/bin/bash`

```
$ [sudo] docker run --entrypoint /bin/bash -i -t <image_name>
```

Run an image in interactive mode with the command `/bin/bash` mounting the host director `/var/app/current` to the container directory `/usr/src/app`

```
$ [sudo] docker run -i -t -v /var/app/current:/usr/src/app/ <image_name> /bin/bash
```

Run an image in interactive mode with the command `/bin/bash` setting the environments variables `FOO` and `BAR`

```
$ [sudo] docker run -i -t -e FOO=foo -e BAR=bar <image_name> /bin/bash
```