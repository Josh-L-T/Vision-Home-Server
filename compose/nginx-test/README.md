# Nginx Compose Test

This example maps Nginx to Vision's loopback address on port 8080. In an
SSH session on Vision, open this directory and validate the file.

```sh
sudo docker compose -f compose.yaml config
```

After validation succeeds, start the container and check its status and
HTTP response from Vision.

```sh
sudo docker compose -f compose.yaml up -d
sudo docker compose -f compose.yaml ps
curl -I http://127.0.0.1:8080/
```

Expect a running Nginx container and an HTTP 200 response. To remove the
test container when finished, run:

```sh
sudo docker compose -f compose.yaml down
```
