# companion-module-allenheath-dlive-ilive

See [HELP.md](HELP.md) and [LICENSE](LICENSE) for more information about this module.

This module for the Allen & Heath dLive and iLive can control parameters of the console
via MIDI and TCP (dLive only) commands over IP

Modified by Andrew Broughton in 2020 from original dLive module.
iLive functions by Matt Andrewartha

Current Version 2.0.3

## Experimental iLive AHNet build

This local development build adds early iLive AHNet meter support.

Current test package:

```text
allenheath-dlive-ilive-2.0.3.tgz
```

The AHNet work is based on live iLive testing and should be treated as a tester build, not final protocol documentation.

Early iLive AHNet support includes:

- input Post PreAmp/Trim, Post Gate/PEQ, Post Compressor, Post Limiter/De-Ess, and Post Delay meters
- input gate, compressor, and limiter gain-reduction meters
- Aux 1-6 and Main L/R meters, indexed from the configured iLive mix layout
- input channel names and colours
- detected iLive mix configuration variables
- active-page meter subscriptions to reduce load

N.B. as of 2025, I (Andrew Broughton) no longer maintain or supports this module. (I no longer own a dLive product)
