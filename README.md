# Home Assistant Addon - Netcup DynDNS for FRITZ!Box

This addon provides a simple proxy api that can be used to update dns records in Netcup CCP with the built-in FRITZ!Box dynamic dns feature.

## Using the FRITZ!Box DynDNS Client

**Configuration**

The following configuration properties need to be set:

|Property|Description|
|-|-|
|`netcupCustomerNumber`|Netcup customer number|
|`netcupApiKey`|API key generated in Netcup CCP|
|`netcupApiPassword`| API password generated in Netcup CCP|
|`fritzBoxApiPassword`|Any password (will be used later when adding config in FRITZ!Box )|

**Setting up DynDNS in the FRITZBox!**

- Open the FRITZ!Box web interface
- Navigate to `Internet -> Freigaben -> DynDNS`
- Fill the form as described below

|Property|Description|
|-|-|
|DynDNS-Anbieter|Choose `Benutzerdefiniert`|
|Domainname|Your domain name, e.g. `example.com`|
|Benutzername|Not used by the web service|
|Kennwort|Password set via `fritzBoxApiPassword` variable|
|Update-URL|Update URL with placeholders that will be substituted by the FRITZ!Box: `homeassistant.local:8000/update?domain_name=<domain>&ipv4=<ipaddr>&password=<pass>`|
