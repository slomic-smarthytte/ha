# Smarthytte - Home Assistant installation
> This repo contains installation and configuration files for Home Assistant used at Slomic Smarthytte and 
> is based on the official [docker-compose](https://www.home-assistant.io/installation/linux#docker-compose)
> installation creating two containers: 1) `homeassistant` and 2) [`zwave-js-ui`](https://github.com/zwave-js/zwave-js-ui)
> (more details at [HA Z-Wave JS](https://www.home-assistant.io/integrations/zwave_js/)).
> 
> Note! Since I'm running HA on Intel NUC, I have chosen to use the [intel-nuc-homeassistant](https://hub.docker.com/r/homeassistant/intel-nuc-homeassistant),
> docker image, however you can easily change the docker image to your hosting platform by choosing 
> another official docker image from [homeassistant](https://hub.docker.com/u/homeassistant).
> 
> The purpose of this repo is to share the general installation setup, configurations and automations and not 
> to get you up and running with identical setup as mine, since that requires much more then only software setup.

# My hardware
- [Intel Nuc NUC7i7DNK2E Dawson Canyon](https://www.komplett.no/product/1008777), 
  with 250GB SSD disk and 16GB RAM
- [Aeotec Z-wave USB stick (Gen 5+)](https://aeotec.com/z-wave-usb-stick/)

# Secrets
I'm using `secrets.yaml` to store all secrets, as described in [Storing secrets](https://www.home-assistant.io/docs/configuration/secrets/).
You will therefore see `!secret <secret>` references in many configuration files.

# Storing history in InfluxDB
All historical data is stored in InfluxDB and visualized with use of [Grafana](https://github.com/slomic-smarthytte/monitoring),
see also [influxdb.yaml](config/ha/influxdb.yaml). InfluxDB is running as part of the [monitoring](https://github.com/slomic-smarthytte/monitoring)
docker stack.

# Upgrading
I'm upgrading manually by bumping the version number in [docker-compose.yml](./docker-compose.yml) 
and executing `docker-compose up -d`
