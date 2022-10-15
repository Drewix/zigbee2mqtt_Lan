<div align="center">
    <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt">
        <img width="150" height="150" src="zigbee2mqtt/logo.png">
    </a>
    <br>
    <br>
    <div style="display: flex;">
        <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/actions?query=workflow%3ACI">
            <img src="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/workflows/CI/badge.svg">
        </a>
        <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/releases">
            <img src="https://img.shields.io/github/release/zigbee2mqtt/hassio-zigbee2mqtt.svg">
        </a>
        <a href="https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/stargazers">
            <img src="https://img.shields.io/github/stars/zigbee2mqtt/hassio-zigbee2mqtt.svg">
        </a>
        <a href="https://discord.gg/dadfWYE">
            <img src="https://img.shields.io/discord/556563650429583360.svg">
        </a>
        <a href="http://zigbee2mqtt.discourse.group/">
            <img src="https://img.shields.io/discourse/https/zigbee2mqtt.discourse.group/status.svg">
        </a>
    </div>
    <h1>NON Official Zigbee2MQTT Home Assistant addon</h1>
</div>
This is a copy made to be able to use multiple instances in HA. Original Source: https://github.com/zigbee2mqtt/hassio-zigbee2mqtt#installation
## Installation
1. If you don't have a MQTT broker yet; in Home Assistant go to **Settings → Add-ons → Add-on store** and install the **Mosquitto broker** addon.
1. Go back to the **Add-on store**, click **⋮ → Repositories**, fill in</br>  `https://github.com/zigbee2mqtt/hassio-zigbee2mqtt` and click **Add → Close**.
1. The repository includes two add-ons:
    - **Zigbee2MQTT** is the stable release that tracks the released versions of Zigbee2MQTT. (**recommended for most users**)
    - **Zigbee2MQTT Edge** tracks the `dev` branch of Zigbee2MQTT such that you can install the edge version if there are features or fixes in the Zigbee2MQTT dev branch that are not yet released.
1. Click on the addon and press **Install** and wait till the addon is installed.
1. Click on **Configuration**
    - If you are **not** using the Mosquitto broker addon fill in your MQTT details (leave empty when using the Mosquitto broker addon). Format can be found [here](https://www.zigbee2mqtt.io/guide/configuration/mqtt.html#server-connection), but skip the initial `mqtt:` indent. e.g.: <br>
        ```yaml
        server: mqtt://localhost:1883
        user: my_user
        password: my_password
        ```
    - Fill in the serial details (e.g. port of your USB coordinator). Format can be found [here](https://www.zigbee2mqtt.io/guide/configuration/adapter-settings.html#adapter-settings), but skip the initial `serial:` indent. e.g.: <br>
        ```yaml
        port: /dev/ttyUSB0
        ```
    - If you don't know the port and you have just one USB device connected to your machine try `/dev/ttyUSB0`. Else use the [Home Assistant CLI](https://www.home-assistant.io/common-tasks/os#home-assistant-via-the-command-line) and execute `ha hardware info` to find out. 
    - Click **Save**
    - **Tip:** it is possible to refer to variables in the Home Assistant `secrets.yaml` file (not the Zigbee2MQTT one!) by using e.g. `password: '!secret mqtt_pass'`
1. Start the addon by going to **Info** and click **Start**
1. Wait till Zigbee2MQTT starts and press **OPEN WEB UI** to verify Zigbee2MQTT started correctly.
    - If it shows `502: Bad Gateway` wait a bit more and refresh the page.
    - If this takes too long (e.g. 2 minutes +) check the **Log** tab to see what went wrong.

For more information see [the documentation](https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/blob/master/zigbee2mqtt/DOCS.md).

## Changelog
The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).

All notable changes to this project will be documented in the [CHANGELOG.md](zigbee2mqtt/CHANGELOG.md) file.

Version for releases is based on [Zigbee2MQTT](https://github.com/Koenkk/zigbee2mqtt) format: `X.Y.Z`.

Any changes on the addon that do not require a new version of Zigbee2MQTT will use the format: `X.Y.Z-A` where `X.Y.Z` is fixed on the Zigbee2MQTT release version and `A` is related to the addon.

Edge version will not maintain a CHANGELOG and doesn't have a version.

## Issues
If you find any issues with the add-on, please check the [issue tracker](https://github.com/zigbee2mqtt/hassio-zigbee2mqtt/issues) for similar issues before creating one. If your issue is regarding specific devices or, more generally, an issue that arises after Zigbee2MQTT has successfully started, it should likely be reported in the [Zigbee2MQTT issue tracker](https://github.com/Koenkk/zigbee2mqtt/issues).

Feel free to create a PR for fixes and enhancements. 

## Credits
- [danielwelch](https://github.com/danielwelch)
- [ciotlosm](https://github.com/ciotlosm)
- [Koenkk](https://github.com/Koenkk)
