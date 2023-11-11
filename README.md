# UniFi Controller

This is my custom docker config for [linuxserver/unifi-network-application](https://github.com/linuxserver/docker-unifi-network-application)

1) Install docker.

2) Run the following script.

This will create a docker project running the mongo db service and the unify network app service.

```sh
touch ~/Unifi # Create directory to store persistant data.
docker compose up -d
```

3) browse to https://localhost:8443

## Notes

- Watch this fantastic video about how to setup the Controller: https://www.youtube.com/watch?v=cxfHyjXKr0k