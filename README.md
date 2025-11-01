# Neuro-sama Lava Lamp for Home Assistant

Here's a guide on how to add the Neuro-sama Lava Lamp to Home Assistant.

## Prerequisites

- [Home Assistant](https://home-assistant.io)
- [Tuya Local integration](https://github.com/make-all/tuya-local)

## Setup

1. Add the lamp in the Swarm Sync app if you haven't already.
2. Turn on troubleshooting mode in Settings, then copy the debug logs and paste them in your preferred text editor.

<img src="./assets/step2.jpeg" width="256"></img>

3. Get your local key by searching your logs for `localKey` and copying the 16-character string next to it without the quotes. For example, if your log looked like this:

```
,"localKey":"a1bc2de345fg6789",
```

Your local key would be `a1bc2de345fg6789`.

4. Get the device ID by searching the logs again for `devId` and following the same instructions above, or, in the Swarm Sync app, open the device controls and look under the name of your lamp, that's also your device ID.
5. If you haven't used Tuya Local before, click the button below to download the integration in HACS, then restart Home Assistant.

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=make-all&repository=tuya-local&category=integration)

6. Download the config by right clicking [this link](https://github.com/IceBotYT/ha-neuro-lamp/raw/refs/heads/main/assets/neuro_lavalamp.yaml) and clicking "Save link as...".
7. Put the config file in your Home Assistant config under `/config/custom_components/tuya_local/devices`.
8. Restart Home Assistant.
9. Start the config flow by clicking the button below.

[![Add Integration to your Home Assistant
instance.](https://my.home-assistant.io/badges/config_flow_start.svg)](https://my.home-assistant.io/redirect/config_flow_start/?domain=tuya_local)

10. In the config flow, choose "Manually provide device connection information."
11. Enter your device ID and local key from before, and choose protocol version 3.5.
12. On the next screen, open the dropdown and choose the new device you put in your config called `neuro_lavalamp`.
13. Name your device and configure an area.

## Stream Sync

1. Import the blueprint by clicking the button below:

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FIceBotYT%2Fha-neuro-lamp%2Fraw%2Frefs%2Fheads%2Fmain%2Fassets%2Fneuro_lamp_stream_sync.yaml)

2. Configure the blueprint by adding your new lamp and clicking Save.
3. You now have a script that will turn on Stream Sync by just running it. You can put it on your dashboard or run it however you like.

## Problems pairing?

Try the troubleshooting available [here](https://swarmsync.app/support.html). Otherwise, join [the Discord](https://discord.gg/neurosama) and check the pinned messages in [this forum post](https://discord.com/channels/574720535888396288/1426970657631113376) for the most up to date information.

## Credits

Thank you to [@Sqbika](https://github.com/Sqbika) for providing the device config and script for turning on Stream Sync!
