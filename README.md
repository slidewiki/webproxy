# SlideWiki Web Proxy #

This Docker image is based on [nginx-proxy](https://github.com/jwilder/nginx-proxy). It adds a `maintenance` command that allows for temporarily activating an nginx configuration that redirects all requestes to a maintenance info page. 

Switch to maintenance mode: `docker exec webproxy maintenance on`
Switch to normal operation: `docker exec webproxy maintenance off`

Additional to the sharing the host's Docker socket for docker-gen the `BASENAME` environment variable has to be set to the base domain name of the instance. 

`docker run -d --name proxy -p 80:80 -v /var/run/docker.sock:/tmp/docker.sock:ro -e BASENAME=slidewiki.org slidewiki-webproxy`


