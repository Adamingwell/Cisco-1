# `no ip domain-lookup`

[Back to Cisco 1 Class Notes](Startup.md)

## What it does

This Cisco IOS global configuration command disables the device's DNS-based hostname lookups. DNS (Domain Name System) translates names into IP addresses. With lookups enabled, IOS may treat an unrecognized command at the EXEC prompt as a hostname, show `Translating...`, and wait for a DNS response. Turning lookups off lets IOS return an error immediately for that kind of typo.

## Enter it on a switch or router

```text
Switch> enable
Switch# configure terminal
Switch(config)# no ip domain-lookup
Switch(config)# end
Switch# copy running-config startup-config
```

Type only the text after each prompt. The `#` is part of the prompt. The command takes effect immediately. The last line saves the configuration so it survives a restart. If IOS rejects the hyphenated form, use `no ip domain lookup` in global configuration mode.

## Check it and turn it back on

At the EXEC prompt, try a made-up command such as `zztest`. IOS should return an error without waiting on `Translating...`. A ping to a numeric address such as `ping 192.168.1.1` can still work if the address is reachable. A hostname that requires DNS will no longer resolve from this device.

To re-enable DNS lookups, enter `ip domain-lookup` (or `ip domain lookup`) in global configuration mode. If the device needs to resolve hostnames, configure a reachable DNS server with `ip name-server`.

**Study takeaway:** `no ip domain-lookup` disables DNS lookups by the Cisco device and prevents the wait caused by unrecognized EXEC commands.

[Cisco documentation](https://www.cisco.com/c/en/us/support/docs/routers/10000-series-routers/46253-ipdomain-lookup.html)
