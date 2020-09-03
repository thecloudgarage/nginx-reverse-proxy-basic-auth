# USE NGINX AS REVERSE PROXY IN DOCKER & CLOUD FOUNDRY
* git clone this repository on a Ubuntu 18.04 and in the parent directory

```
sudo apt-get install apache2-utils
sudo htpasswd -c .htpasswd <username>
```
* htpasswd will prompt for password
* nginx.conf sample is provided (alter the proxy pass directive for your backend., if the app is on cloud foundry then paste the cf app route in http mode)
* Once done, just run

```
docker build -t <image-name> .
docker tag <image-name> <docker-hub-username/<image-name>
docker login
docker push <docker-hub-username/<image-name>
```

* Once done and if you want to render a basic http auth reverse proxy in cloud foundry., then

```
cf login
cf push <unique-app-name> --docker-image <docker-hub-username/<image-name>
```

* Test the reverse proxy with authentication
* Add users to increase the authentication scope



