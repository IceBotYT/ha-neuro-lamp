# Neuro-sama Lava Lamp for Home Assistant

Here's a guide on how to add the Neuro-sama Lava Lamp to Home Assistant.

## Prerequisites

- [Smart Life app](https://smartapp.smart321.com/smartlife)
- [Home Assistant](https://home-assistant.io)
- [LocalTuya integration](https://github.com/xZetsubou/hass-localtuya/)

## Setup

1. Create a Smart Life account in the app.
2. If you've already set up the lava lamp before, reset it:
    - Unplug it, wait 2-3 seconds, then replug it.
    - Repeat this at least 3 times until you see the lamp flash when it starts.
    - If done correctly, the lamp will start to flash red to indicate it is in pairing mode.
3. Open the Smart Life app, and the lava lamp should show up automatically with the name "LED蜡灯".
4. Tap Add, input your Wi-Fi credentials, and make sure it pairs successfully.
5. Once paired, the lamp should show up in the app. You can test it here to make sure control of it works.
6. Now, follow the steps [here](https://xzetsubou.github.io/hass-localtuya/cloud_api/) to create your Tuya IoT Platform account.
7. Once your account is created, follow the steps [here](https://xzetsubou.github.io/hass-localtuya/usage/installation/) to set up the LocalTuya integration.
8. Now, download the entity template. Right click [this link](https://github.com/IceBotYT/ha-neuro-lamp/raw/refs/heads/main/assets/Neuro_Lamp.yaml), click "Save link as..." and put it into your config under `/config/custom_components/localtuya/templates`. Then, restart Home Assistant.
9. Open the configuration like so:
![Configuration menu for LocalTuya](./assets/step8.png)
10. Click Add new device.
11. Here, hopefully your lamp should've been automatically discovered. If it has, choose it in the menu, click submit, and skip to step 14.
12. If it wasn't automatically discovered, get your local key and ID by using [TuyAPI](https://github.com/codetheweb/tuyapi).
    - First, make sure [Node.JS is installed](https://nodejs.org/en/download).
    - Install the TuyAPI CLI by running `npm i @tuyapi/cli -g`.
    - Run `tuya-cli wizard` and input the prompted information. You can find a device ID both on the [Tuya IoT Platform](https://platform.tuya.com) website or in the Smart Life app.
13. Use your local key and device ID from the CLI to fill out the form like so (leave all optional fields blank):
![LocalTuya configuration](./assets/step12.png)

If this doesn't work, try setting Protocol Version to 3.5!

14. Once connected successfully, click "Use saved template" and choose your new `yaml` file you imported in step 8.
15. Keep clicking Submit until you see the success screen.

Congratulations! Your lava lamp is now ready to be used.

## Stream Sync?

I've yet to confirm it, but if you set the effect to Music, it should sync to stream. I will update this as soon as I know if it works.

## Problems pairing?

Try resetting it by rapidly plugging and unplugging the lamp 3 times. Otherwise, join [the Discord](https://discord.gg/neurosama) and check the pinned messages in [this forum post](https://discord.com/channels/574720535888396288/1426970657631113376) for the most up to date information.
