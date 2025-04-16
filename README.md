<h1 align="center">FestFx (HASSIO VJ Controller)</h1>
<p align="center"><br /><img src="https://github.com/user-attachments/assets/aba70cd4-4a07-4a9f-8d81-09e8df8016a0/" width="620"></p>

## Features

Control LedFX/WLED live like a VJ, designed for touch interface (tablet, mobile). Preview/edit effects before activating them live. <i>UI: red (slider), green (toggle), blue (select).</i>

<table>
<tr>
<th align="center">
  Live lights
</th>
<th align="center">
    Preview lights (settings)
</th>
</tr>
<tr>
<td>
  
**Header**
  <ul>
    <li><b>Live effect name</b>
    <li><b>Playlist:</b> Start Auto Mode</li>
    <li><b>Force:</b> Prevent a [touch action] on an effect/Preset (do a [hold action] instead)</li>
    <li><b>Live effect</b>
    <li><b>Tabs:</b> Switch between different modes</li>
  </ul>
  
**Main - Effects**
  <ul>
    <li><b>Effects:</b> [touch action] activate live, [hold action] preview/edit the effect</li>
  </ul>
  
**Main - Presets**
  <ul>
    li><b>Presets:</b> [touch action] activate live, [hold action] preview/edit the preset</li>
    <li><b>Save:</b> Save mode, save current effect to a preset</li>
    <li><b>Rename:</b> Rename mode, rename a Preset</li>
    <li><b>Playlist:</b> Playlist mode, set a preset to 'verse', 'build-up' or 'chorus' for auto mode</li>
    <li><b>Waves:</b> Waves mode, always show playlist type</li>
    <li><b>Current colors:</b> When activating a preset, use the current color (in settings) instead of saved color</li>
    <li><b>Current brightness:</b>  When activating a preset, use the current brightness (in settings) instead of saved brightness</li>
  </ul>
</td>
<td valign="top">
  
**Header**
  <ul>
    <li><b>Preview effect name</b>
    <li><b>Sync:</b> Green if the preview/edditing == live </li>
    <li><b>Direct:</b> Changing a parameter is directly actived live mode</li>
    <li><b>Launch:</b> Activate preview settings to live</li>
    <li><b>Preview effect</b>
    <li><b>Quick colors:</b> Color presets [touch] activate colors, [hold] save current colors to preset</li>
    <li><b>(Background) Colors:</b> Set colors (low, mid, high, color, color brightness, background, background brightness</li>
  </ul>
  
**Main**
  <ul>
    <li><b>Parameters:</b> Change effect parameters</li>
  </ul>
</td>
</tr>
</table>

## Installation
1. **Install HACS:** <i>'Vertical Stack In Card', 'Bubble Card', 'card-mod', 'browser_mod'</i>
2. **Install Services:** <i>'RESTful command', 'MQTT'</i>
3. Copy the repository files to HA '/config' folder
4. Change text within the files:
   - the URL's in '/festfx/scripts_rest.yaml' and '/www/' files ([LedFx API](https://docs.ledfx.app/en/latest/api.html))
   - Add the following to your config file:
     ```
     rest_command: !include festfx/scripts_rest.yaml
     homeassistant:
       packages: !include_dir_named festfx
     ```
5. Copy YAML from the dashboard file ('/config/festfx-dashboard/') into a new dashboard and apply the FestFx theme
6. Restart HA
