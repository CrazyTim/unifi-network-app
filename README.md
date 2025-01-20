# UniFi Network App

This is my docker config to install the UniFi network app in a few simple steps. It uses the docker image [linuxserver/unifi-network-application](https://github.com/linuxserver/docker-unifi-network-application).

## Getting started

1) Decide where UniFi should save persistant data on your machine. By default it is `~/Unifi` and this can be changed in the `.env` file.

2) Install Docker Desktop and run the following script. This will create a docker project running the mongo db and the UniFi network app.

```sh
docker compose up -d
```

3) Browse to https://localhost:8443 and complete the initial setup. Sign in using your Unifi account (https://unifi.ui.com)

4) If this is the first time you are signing in, or if your machine's IP address has changed, go to "Settings" > "System" > "Advanced" > "Inform Host" and tick "Override". Enter the IP address of your machine, then restart the docker project. This step is needed because UniFi is running inside Docker and this makes it accessible to the devices. If you noice that devices are not adopted anymore, then its probably because your machine's IP address has changed.

## Notes

- Watch this fantastic video about how to configure the UniFi Controller: https://www.youtube.com/watch?v=cxfHyjXKr0k

- If something goes wrong, check the logs in `~/Unifi/config/logs/`