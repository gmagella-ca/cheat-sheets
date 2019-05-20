# Docker cheat-sheet

These are some handy docker commands (use of sudo is not required if you have appropriate permissions):

Build a docker image:
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

run an image exposing port 80 to your localhost 8080
```
$ [sudo] docker run -d <image_name> -p 8080:80
```

Hop inside the container (like SSH) being able to hop off (note: for alpine use /bin/sh):
```
docker exec -it <mycontainer> /bin/bash
```

Run an image in interactive mode with the command `/bin/bash`

```
$ [sudo] docker run -i -t <image_name> /bin/bash
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