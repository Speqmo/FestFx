<h1 align="center">FestFx</h1>

## Features

Control LedFX/WLED live like a VJ, designed for touch interface (tablet, mobile).

- **Preview**: Preview effects before activating

- **Presets**: Save effects for quick activation

- **Auto**: Upcomming...

## Installation

HACS: 'Vertical Stack In Card', 'Bubble Card', 'card-mod', 'browser_mod'

Services: 'RESTful command', 'MQTT',

Files:
- Copy the files to HA '/config' folder
- Change the URL's in '/festfx/scripts_rest.yaml' and '/www/' files ([LedFx API](https://docs.ledfx.app/en/latest/api.html))
- Copy YAML from the dashboard file ('/config/festfx-dashboard/') into a new dashboard and apply the FestFx theme
- Add the following to your config file:
```
rest_command: !include festfx/scripts_rest.yaml
homeassistant:
  packages: !include_dir_named festfx
```

Restart HA
