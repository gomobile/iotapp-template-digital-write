Intel® XDK IoT Node.js\* Digital Pin Write App
==============================================
See [LICENSE.md](LICENSE.md) for license terms and conditions.

This sample application is distributed as part of the
[Intel® XDK](http://xdk.intel.com). It can also be downloaded
or cloned directly from its git repo on the
[public Intel XDK GitHub\* site](https://github.com/gomobile).

For help getting started developing applications with the
Intel XDK, please start with
[the Intel XDK documentation](https://software.intel.com/en-us/xdk/docs).

App Overview
------------
A simple Node.js application that writes to an onboard digital output (a GPIO
output), on select Intel IoT development boards, and displays the written
value to the console log.

The app initializes a single pin to digital output mode, so it can be written;
updates that digital output at a regular basis; and prints the result of each
write to the console. The specific pin that is written is configured in
`cfg-app-platform.js` and can be identified by looking for lines similar to the
following line of code, in the `cfg.init` method:

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    io = opt.altPin ? io : 1 ;              // use alternate pin?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In the example shown above, digital "pin 1" will be used for the digital output.

**IMPORTANT:** the pin that is configured by the sample is a function of the
detected board. You **must** inspect the code to determine which pin is being
configured for use on your board!!

Once you have identified the GPIO pin that is being written, you can use a jumper
wire and a scope or digital multimeter to monitor the voltage of that digital
output, by connecting one end of the jumper wire to the digital output and the
other end of the jumper to your measurement device.

Most boards have many pins that can be configured for use as a digital output.
The `cfg-app-platform.js` module has been designed so you can override the pin
that is used, by passing it an alternate pin during the init call (see the module
documentation). Or, you can simply modify the code to change the default value.

Important Sample App Files
--------------------------
* main.js
* package.json

Important Sample Project Files
------------------------------
* README.md
* LICENSE.md
* project-name.xdk
* project-name.xdke

Tested IoT Node.js Platforms
----------------------------
* [Intel® Galileo Board](http://intel.com/galileo)
* [Intel® Edison Development Platform](http://intel.com/edison)
* [Intel® Joule™ 570x Developer Kit](http://intel.com/joule)
