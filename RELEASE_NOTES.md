# Test Package Notes

## allenheath-dlive-ilive 2.0.3 AHNet tester build

This is an experimental tester package for Allen & Heath iLive AHNet meter support in the dLive/iLive Companion module.

Package:

```text
allenheath-dlive-ilive-2.0.3.tgz
```

## Added

- Optional iLive AHNet meter client using TCP `51321` and UDP `51324`.
- Input meter feedbacks and variables:
  - Post PreAmp/Trim
  - Post Limiter/De-Ess
  - Gate gain reduction
  - Compressor gain reduction
  - Limiter gain reduction
- Output meter feedbacks and variables:
  - Aux 1-6
  - Main Left/Right
- iLive input channel name and colour lookup for active meter/preset channels.
- Dark channel-colour background feedback for iLive input fader presets.
- Yamaha-RCP-style fader button/knob presets with fader meters and gain-reduction meters.
- Active AHNet subscriptions so only visible/active button feedbacks subscribe to their required meter banks and channel names.
- Detected iLive mix configuration variables.
- Configurable AHNet graphical meter refresh and dB text refresh intervals.

## Known Limitations

- Meter dB scaling is approximate.
- AHNet protocol mapping is based on live reverse-engineering and needs more console/firmware validation.
- Companion image feedback rendering can feel slower than iLive Editor native meters.
- iLive Editor and Companion can both connect, but AHNet session ids and UDP source ports are dynamic.

## Validation

The local tester package was built with:

```bash
node --check ahnet-meters.js && node --check index.js
npx companion-module-check
node node_modules/@companion-module/tools/scripts/build-connection.js --dev
```

