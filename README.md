# Owie Flashing Tool

A static web page that flashes [Owie](https://github.com/lolwheel/Owie) firmware onto an ESP8266 over Web Serial, using [esp-web-tools](https://esphome.github.io/esp-web-tools/).

Live page: <https://radimklaska.github.io/owie-flashingtool/>

## How it works

`index.html` fetches releases from the GitHub API at load time and renders one install button per release that ships a `firmware.bin` asset. The `latest` and `pre-release` badges match GitHub's own labeling.

## Picking a firmware source

The page defaults to [`radimklaska/owie`](https://github.com/radimklaska/owie). You can switch sources in two ways:

- **Dropdown** — pick `lolwheel/Owie`, `ow-breaker/Owie`, or `Other…` to type any `owner/Repo`.
- **URL parameter** — append `?repo=owner/Repo`, e.g. `?repo=lolwheel/Owie`. The dropdown and URL stay in sync.

The target repo must publish releases whose assets include a file literally named `firmware.bin`.

## Requirements

A Chromium-based browser (Chrome, Edge, Opera) on desktop — Web Serial is not supported in Firefox or Safari. You may also need [USB-to-serial drivers](https://esphome.github.io/esp-web-tools/#drivers).

## Local development

It's a single file. Open `index.html` in a browser, or serve the directory with any static server (e.g. `python3 -m http.server`). esp-web-tools is loaded from unpkg, so no build step is required.
