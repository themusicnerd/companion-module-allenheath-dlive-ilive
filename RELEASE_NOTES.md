# Release Notes

## allenheath-dlive-ilive 2.0.3 AHNet support

This release adds tested Allen & Heath iLive AHNet meter support to the dLive/iLive Companion module.

Package artifact:

```text
allenheath-dlive-ilive-2.0.3.tgz
```

## Added

- Optional iLive AHNet meter client using TCP `51321` and UDP `51324`.
- Input meter feedbacks and variables:
  - Post PreAmp/Trim
  - Post Gate/PEQ
  - Post Compressor
  - Post Limiter/De-Ess
  - Post Delay
  - Gate gain reduction
  - Compressor gain reduction
  - Limiter gain reduction
- Output meter feedbacks and variables:
  - Aux 1-6, indexed from the configured iLive mix layout
  - Main Left/Right, indexed from the configured iLive mix layout
- iLive input channel name and colour lookup for active meter/preset channels.
- Dark channel-colour background feedback for iLive input fader presets.
- Yamaha-RCP-style fader button/knob presets with fader meters and gain-reduction meters.
- Active AHNet subscriptions so only visible/active button feedbacks subscribe to their required meter banks and channel names.
- Detected iLive mix configuration variables.
- Configurable AHNet graphical meter refresh and dB text refresh intervals.
- Avoids recurring UDP keepalives to the iDR setup port after the initial AHNet UDP hello.
- iLive AHNet mix-layout detection now stays internal instead of writing detected counts back into manual dLive mix-count config fields.
- Config fields include tooltips for connection, AHNet, fader fade, and dLive mix-layout settings.
- Advanced settings hide fixed protocol ports, meter/fade timing, dLive MIDI channel, and dLive manual mix-layout fields from normal setup.

## Known Limitations

- Input level meter dB scaling is approximate.
- Input gate, compressor, and limiter gain-reduction scaling is based on live Channel 1 tests: raw values map closely to `(65535 - raw) / 256` dB, with raw `13/14` meaning zero reduction. Graphical GR meters use a 0-30 dB scale.
- Companion image feedback rendering can feel slower than iLive Editor native meters.
- iLive Editor and Companion can both connect, but AHNet session ids and UDP source ports are dynamic.

## Validation

The package was built with:

```bash
node --check ahnet-meters.js && node --check index.js
npx companion-module-check
node node_modules/@companion-module/tools/scripts/build-connection.js --dev
```
