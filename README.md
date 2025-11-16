# OpenHAB Bindings

This repository contains test bindings for openHAB.

Currently there are bindings for
- org.openhab.binding.smainverterbluetooth
- org.openhab.binding.sunsynk (this is an update and will included in the next openHAB release 5.1.0)

## smainverterbluetooth
This is a new binding see the [read.me](https://github.com/LeeC77/OpenHAB_5_0_0_test_bindings/blob/main/readmes/smainverterbluetooth.md)

## sunsynk
 See [readme](https://github.com/LeeC77/OpenHAB_5_0_0_test_bindings/blob/main/readmes/sunsynk.md)
### Issues Resolution

#### Client authorisation breaking changes

Sun Synk have released a new App that uses the same server, as a consequence (since Thursday 13th November) the client application now needs to authorise before user credential can be submitted for login authorisation.

 * The client application authentication uses GET with a Nonce, a source and an signature to construct an end point to obtain a [sunsynk] public key. The signature is an MD5 hash of the end point data and a shared secret.
 * A (plain text) password is salted and RSA encrypted with the public key and POSTed with the user name etc to obtain an access and refresh token that are then used as before.

#### Channel update issues

[OpenHAB Community Issue](https://community.openhab.org/t/new-sun-synk-connect-account-and-inverter-binding/155680/8?u=leec77)

Add the org.openhab.binding.sunsynk-5.0.0.jar or org.openhab.binding.sunsynk-5.1.0-SNAPSHOT.jar to your openHAB addons directory
Check that
* Battery Current
* Battery Power
* Battery Voltage
now populate correctly with values.

### Binding Enhancement Support for solar

Support for
* Grid frequency
* Solar String 1 Voltage, Current and Power
* Solar String 2 Voltage, Current and Power
* Solar Energy today, this month, this year  and total
* Solar Efficiency and current ac-power
* Inverter capacity
