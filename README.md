# UniFi Network App

How to install the UniFi Network app on your machine with docker in a few simple steps. Only basic knowledge of the terminal, git, and networking are required.

Add a couple of UniFi WiFi access points (APs), for example UAP-AC-LITE, and you'll have your own meshing home network!

Uses [linuxserver/unifi-network-application](https://github.com/linuxserver/docker-unifi-network-application).

## Getting started

1) Install Docker Desktop.

2) Clone this repo.

3) Open your terminal. Change directory to the repo and run the folowing script. This will create a docker project running the UniFi network app.

  ```sh
  docker compose up -d
  ```

4) Browse to https://localhost:8443 and complete the initial setup. Sign in using your Unifi account (https://unifi.ui.com)

5) If this is the first time you are signing in, go to "Settings" > "System" > "Advanced" > "Inform Host" and tick "Override", and enter the IP address of your machine and apply the changes. This step is needed because UniFi is running inside Docker and this makes it accessible to the devices.

6) If your machine's IP address changes again, or if you notice that the UniFi devices are not adopted anymore, then repeat step 5, and wait for a few minutes for the system to refresh or until all the devices have all been re-adopted.

## Notes

- To create a WiFi mesh, Go to "Settings" > "WiFi" and create a new network. Assign as many APs as you want to the network. They will all broadcast the same SSID (or network name). You will be automatically connected to the AP with the strongest signal.

- Watch this fantastic video about how to configure the UniFi Controller: https://www.youtube.com/watch?v=cxfHyjXKr0k

- If something goes wrong, check the logs in `~/Unifi/config/logs/`

- Persistant data will be saved in `~/Unifi` (you can backup this folder!), and this directory can be changed in the `.env` file if you want.