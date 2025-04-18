<h1 align="center">FestFx VJ Controller</h1>
<p align="center"><a href="https://drive.google.com/file/d/1rfztbmAcchIlFwV3GrhHJQY5YvWO3wKC"><img width="200" src="https://github.com/user-attachments/assets/aba70cd4-4a07-4a9f-8d81-09e8df8016a0/"></a></p>
<h2>Become a VJ - (or let the computer take over)</h2> 

With <a src="https://github.com/Speqmo/FestFx">FestFx</a>, you can control LED strips and lights live, like a VJ - something LedFx isn’t really suited for. FestFx is designed to act as a bridge between <a src="https://github.com/LedFx/LedFx">LedFx</a> and countless integrations, enabling greater control over things like: presets (e.g. choosing your own color instead of using the one stored in the preset), more advanced auto play modes (playing effects based on music segments like verse, build-up, and chorus), and other extended functionalities. 

The aim is to develop an advanced, VJ-worthy interface that can be controlled by anyone and supports both manual and (semi-)automatic control. The interface is designed for tablets but can also be used via smartphones, Zigbee controllers, MIDI controllers, and more.</p>

## What you need

LedFx was developed for Home Assistant because it’s a stable system that allows fast development and offers countless built-in options to connect different systems. This enables endless functionality — for example, automatically changing light colors based on the album art of the current track. All you need to use FestFx is Home Assistant and LedFx.

- [Home Assistant](https://www.home-assistant.io/installation/) can be easily installed on a wide range of devices: Home Assistant’s own hardware, Raspberry Pi, macOS, Windows, ODROID, Generic x86-64, Linux, and more.

- [LedFx](https://github.com/LedFx) is an awesome piece of software that actually controls the lights - synced to the music! - and is just as easily installed on a computer or Raspberry Pi.


## Manual
Below you can find an image of the interface and explanations of some controls. The current version is stable and serves as a concept to explore the feasibility of our plans. In the short term, the interface will be improved and new features will be added. The colors indicate the type of control: red (slider), green (toggle), blue (select).

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
    <li><b>Presets:</b> [touch action] activate live, [hold action] preview/edit the preset</li>
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
   - The URL's in '/festfx/scripts_rest.yaml' and '/www/' files ([LedFx API](https://docs.ledfx.app/en/latest/api.html))
   - Add the following to your config file:
     ```
     rest_command: !include festfx/scripts_rest.yaml
     homeassistant:
       packages: !include_dir_named festfx
     ```
5. Copy YAML from the dashboard file ('/config/festfx-dashboard/') into a new dashboard and apply the FestFx theme
6. Restart HA
