How to show a Docker container's log? you may think that's easy,just like:
```
docker logs --tail=100 containerid
```
But if we want to view the begaining of the log file? 
```
$docker logs -h
Flag shorthand -h has been deprecated, please use --help

Usage:	docker logs [OPTIONS] CONTAINER

Fetch the logs of a container

Options:
      --details        Show extra details provided to logs
  -f, --follow         Follow log output
      --since string   Show logs since timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)
      --tail string    Number of lines to show from the end of the logs (default "all")
  -t, --timestamps     Show timestamps
      --until string   Show logs before a timestamp (e.g. 2013-01-02T13:23:37) or relative (e.g. 42m for 42 minutes)
```
Aaha, --since and --until nice work. But when we look it at server the --until option is missing.
Show dockr vision
```
Docker version 17.03.2-ce
```
shitttt.


Following is some description of docker log driver configuration.
#### [Configure logging drivers](https://docs.docker.com/config/containers/logging/configure/)
Each Docker daemon have a default logging driver which is [json-file](https://docs.docker.com/config/containers/logging/json-file/).
Show the driver info:
```
docker info --format '{{.LoggingDriver}}'
```

And you can change it with two approaches.
To configure the Docker daemon to default to a specific logging driver.
```
/etc/docker/daemon.json
```
like
```
{
  "log-driver": "json-file",
  "log-opts": {
    "max-size": "10m",
    "max-file": "3",
    "labels": "production_status",
    "env": "os,customer"
  }
}
```

Or configure the logging driver for a container.
```
docker run -it --log-driver none alpine ash
```

With [syslog](https://docs.docker.com/config/containers/logging/syslog/)
and [SyslogServer](https://www.npmjs.com/package/syslog-server)


