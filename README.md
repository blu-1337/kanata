# kanata keyboard config

This repo contains a single [Kanata](https://github.com/jtroo/kanata)-style keyboard remapping configuration in `kanata.kbd`.

## High-level behavior

- **Regular typing stays normal** (tap the letter → the letter).
- Some letters are **tap-or-hold** keys:
  - Tap = type the letter.
  - Hold = temporarily switch into a layer that turns other keys into shortcuts.

## Global config (`defcfg`)

- **`process-unmapped-keys no`**: Kanata does not synthesize events for keys it does not intercept.
  - This reduces risk of modifier “sticking” on some Windows layouts.
- **`windows-altgr add-lctl-release`**: extra Windows safety for layouts where AltGr is implemented as Ctrl+Alt.

## Which keys are intercepted (`defsrc`)

Kanata only “sees” and can remap keys listed in `defsrc`. This config intercepts:

- **Letters**: `q w e r t y u i o p a s d f g h j k l z x c v b n m`
- **Punctuation**: `comma` (`,`), `dot` (`.`)
- **AltGr / Right Alt**: `ralt`

> Note: intercepting `ralt` can reintroduce “stuck Ctrl” issues on *some* Windows keyboard layouts. If you hit that, remove `ralt` from `defsrc` and remove the 4th row from each layer in `kanata.kbd`.

## Layers and chord mappings

### Base layer

Normal typing, plus these special “hold to layer” keys:

- **Hold `A`** → `nav` layer (navigation/editing)
- **Hold `Q`** → `ctrl-nav` layer (tab navigation + ctrl-style editing)
- **Hold `W`** → `wmods` layer (common Ctrl shortcuts)
- **Hold `D`** → `dnums` layer (numbers on letters)
- **Hold `F`** → `fmods` layer (single Esc chord)
- **Hold `Z`** → `zmods` layer (tab management shortcuts)

### `nav` layer (hold `A`)

Navigation and editing keys under the right/left hand:

- **A+W/E/R** → `Home` / `Up` / `End`
- **A+T/Y** → `Backspace` / `Delete`
- **A+S/D/F** → `Left` / `Down` / `Right`
- **A+X** → `Enter`
- **A+C/V** → `Ctrl+Left` / `Ctrl+Right`
- **A+B/N** → `Shift+Left` / `Shift+Right`

### `ctrl-nav` layer (hold `Q`)

Requested Q-chords:

- **Q+S** → `Shift+Tab`
- **Q+F** → `Tab`
- **Q+T** → `Ctrl+Backspace`
- **Q+Y** → `Ctrl+Delete`

Other existing mappings kept from the original config:

- **Q+W** → `PageUp`
- **Q+E** → `Ctrl+Up`
- **Q+R** → `PageDown`
- **Q+D** → `Ctrl+Down`

### `wmods` layer (hold `W`)

Requested common Ctrl shortcuts:

- **W+Z** → `Ctrl+Z`
- **W+X** → `Ctrl+X`
- **W+C** → `Ctrl+C`
- **W+V** → `Ctrl+V`
- **W+A** → `Ctrl+A`
- **W+Y** → `Ctrl+Y`
- **W+S** → `Ctrl+S`

### `dnums` layer (hold `D`)

Number row on letters/punctuation:

- **D+M** → `1`
- **D+,** → `2`
- **D+.** → `3`
- **D+J** → `4`
- **D+K** → `5`
- **D+L** → `6`
- **D+U** → `7`
- **D+I** → `8`
- **D+O** → `9`
- **D+AltGr (`ralt`)** → `0`

### `fmods` layer (hold `F`)

Requested:

- **F+Q** → `Esc`

### `zmods` layer (hold `Z`)

Existing tab-management shortcuts (kept) plus your new requests:

- **Z+S** → `Ctrl+Shift+Tab`
- **Z+D** → `Ctrl+W`
- **Z+F** → `Ctrl+Tab`
- **Z+G** → `Ctrl+T`
- **Z+H** → `Ctrl+Shift+T`
