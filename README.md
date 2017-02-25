# docker vnc qa

Docker image that includes Xvnc, Xvfb and supervisord to simplify running applications based on this image.

## Usage

By default this when this container is run vnc is exposed on port 5900, and the supervisord web interface on port 9001. The default VNC password used by this image is `secret`.

`docker run -d -p 5901:5900 -p 9001:9001 docker-vnc-qa`

## Dockerfile Usage

Example docker file built with this image as the base.

```
FROM docker-vnc-qa:latest

WORKDIR /opt/my-app

ADD . /opt/my-app

COPY bin/supervisor.my-app.conf /etc/supervisord/conf.d/

EXPOSE 8080
```

