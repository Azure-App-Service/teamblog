
# Azure App Service Linux, Runtime Images

App Service Runtime Images are used to run web apps for [Azure App Service](https://docs.microsoft.com/en-us/azure/app-service/containers/app-service-linux-intro) on Linux.

To receive updates on runtimes and versions supported by App Service on Linux,
subscribe to [github.com/Azure-App-Service/teamblog/Announcements](https://github.com/Azure-App-Service/teamblog/Announcements)
tracker.

These images are currently hosted on [DockerHub](https://hub.docker.com/u/appsvc/).

# Supported platforms

Runtime | Version | Image Tag | 
--------|--------|--------|
Python  | 3.7<br />3.6 <br/>2.7 | appsvc/python:3.7_1905242318 <br /> appsvc/python:3.6_1905242318 <br /> appsvc/python:2.7_1905242318 <br /> |
Node.js | 4.4<br /> 4.5 <br/> 4.8 <br />6.2 <br /> 6.6 <br /> 6.9 <br /> 6.10 <br /> 6.11 <br /> 8.0 <br /> 8.1 <br /> 8.2 <br /> 8.8 <br /> 8.9 <br /> 8.11 <br /> 8.12 <br /> 9.4<br /> 10.1 <br /> 10.10 <br /> 10.12 <br /> 10.14 |  appsvc/node:4.4_1905131832 <br /> appsvc/node:4.5_1905131832 <br /> appsvc/node:4.8_1905131832 <br /> appsvc/node:6.2_1905131832 <br /> appsvc/node:6.6_1905131832 <br /> appsvc/node:6.9_1905131832 <br /> appsvc/node:6.10_1905131832 <br /> appsvc/node:6.11_1905131832 <br /> appsvc/node:8.0_1905131832 <br /> appsvc/node:8.1_1905131832 <br /> appsvc/node:8.2_1905131832 <br /> appsvc/node:8.8_1905131832 <br /> appsvc/node:8.9_1905131832 <br /> appsvc/node:8.11_1905131832 <br /> appsvc/node:8.12_1905131832 <br /> appsvc/node:9.4_1905131832 <br /> appsvc/node:10.1_1905131832 <br /> appsvc/node:10.10_1905131832 <br /> appsvc/node:10.12_1905131832 <br /> appsvc/node:10.14_1905131832 <br /> |
.NET Core | 1.0 <br /> 1.1<br /> 2.0 <br /> 2.1 <br /> 2.2 | appsvc/dotnetcore:1.0_1905171704 <br /> appsvc/dotnetcore:1.1_1905171704 <br /> appsvc/dotnetcore:2.0_1905171704 <br /> appsvc/dotnetcore:2.1_1905171704 <br /> appsvc/dotnetcore:2.2_1905171704 |
PHP     | 5.6<br />7.0 <br /> 7.2 <br /> 7.3 |  appsvc/php:5.6.40-apache_1903071319 <br /> appsvc/php:7.0.33-apache_190307131 <br /> appsvc/php:7.2.15-apache_1903071319 <br /> appsvc/php:7.3.2-apache_190307131 <br /> |
Ruby    | 2.3.3 <br /> 2.3.8 <br /> 2.4.5 <br /> 2.5.5 <br /> 2.6.2 |  appsvc/ruby:2.3.3_1903041615 <br /> appsvc/ruby:2.3.8_1903041615 <br /> appsvc/ruby:2.4.5_1903041615 <br /> appsvc/ruby:2.5.5_1903041615 <br /> appsvc/ruby:2.6.2_1903041615 <br /> |

Patches (0.0.**x**) are applied in the next monthly milestone after they are released upstream.

We are currently in the process of upgrading all our runtime images to use Oryx Images as base images. More information about these base images can be found at [Microsoft Oryx GitHub Page](https://github.com/microsoft/Oryx).

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
