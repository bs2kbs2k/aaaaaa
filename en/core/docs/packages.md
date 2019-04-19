# MakeCode packages

Packages are PXT's dynamic/static library mechanism for extending a target, such as the pxt-micro:bit:

> [pxt-microbit](https://github.com/microsoft/pxt-microbit)

Here is an example of a simple package that extends the pxt-microbit target so that the micro:bit can drive a NeoPixel strip:

> [pxt-neopixel](https://github.com/Microsoft/pxt-neopixel)

To see how this package is surfaced, visit https://makecode.microbit.org/ and select the "Extensions" option from the gear menu. You will see the package "neopixel" listed in the available options. If you click on it, a new block category named "Neopixel" will be added to the editor.

In this scenario, PXT dynamically loads the neopixel packages directly from GitHub, compiles it and incorporates it into the web app. Packages also can be bundled with a web app (the analog of static linking). For dynamically loaded packages, targets can provide a white list of approved packages (see [pxtarget.json](/targets/pxtarget#bundleddirs-string-)).

* Got some questions? Join us on our [Community Discord](https://aka.ms/makecodecommunity)!

## Authoring packages

* [Package getting started guide](/packages/getting-started)
* Package configuration via [pxt.json](/packages/pxtJson) file
* [Naming conventions](/packages/naming-conventions)
* [Package versioning](/packages/versioning)
* [Package localization](/packages/localization)
* [Package approval](/packages/approval)

## [Editor extensions](/packages/extensions)

Packages may provide an optional editor extension. An editor extension is an HTML page that gets loaded inside an iFrame by the editor. It allows to interact with the project or access serial data via messages. Package extensions are hosted on [GitHub pages](https://pages.github.com/).