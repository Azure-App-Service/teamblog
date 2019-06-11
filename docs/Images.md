## Build and run an app locally

To build and run an app locally, follow these approximate steps. An example script follows.

```bash
docker pull appsvc/<ImageTag>

docker run \
    -d -it -P \
    --volume $(pwd):/home/site/wwwroot \
    --env PORT=8080 \
    --publish 8080:8080 \
    appsvc/node 

curl localhost:8080

docker exec -it <container> bash
```
