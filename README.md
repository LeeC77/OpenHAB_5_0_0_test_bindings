# Issues Resolution

[OpenHAB Community Issue](https://community.openhab.org/t/new-sun-synk-connect-account-and-inverter-binding/155680/8?u=leec77)

Add the org.openhab.binding.sunsynk-5.0.0.jar to your openHAB addons directory
Check that
* Battery Current
* Battery Power
* Battery Voltage

now populate correctly with values.

# Obtain Solar Response
Set the binding logging level to trace to see the raw responses from SunSynk Connect. 
This can be done via selecting the binding in the addon store and then pressing the cog.
Don't forget to press save.
Open the log viewer in the developers tools and look / search for TRACE events prefixed with org.openhab.binding.sunsynk.internal.api.DeviceController. 
Every minute, assuming default timing the trace for 
* Common Settings
* Grid Real Time Settings
* Battery Real Time Settings
* Temperature History
* Real Time Solar Response

should come around.
Click on Real Time Solar Response and copy the message body for analysis. The response I'm getting without solar panels is below as an example
```
Real Time Solar Response: {"code":0,"msg":"Success","data":{"pac":0,"grid_tip_power":null,"pvIV":[{"id":null,"pvNo":1,"vpv":"2.0","ipv":"0.0","ppv":"0.0","todayPv":"0.0","sn":"2211229948","time":"2025-09-08 21:49:10"},{"id":null,"pvNo":2,"vpv":"2.2","ipv":"0.1","ppv":"0.0","todayPv":"0.0","sn":"2211229948","time":"2025-09-08 21:49:10"}],"mpptIV":[],"etoday":0.0,"etotal":0.0},"success":true}
 ```
Capture a few example and see if you can understand/ relate them to the values in the SunSynk Connect App.
Please provide me with the examples, your understanding and describe how you want to use them.
I suspect the values will be per panel or string, its easier for me if you  want these summarised.

e.g. channels for
* total power (e.g addition of powers)
* average current
* average voltage

# Binding Enhancement

Support for
* Grid frequecy
* Solar String 1 Voltage, Current and Power
* Solar String 2 Voltage, Current and Power 
