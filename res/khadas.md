# KHADAS VIM1S

# vim: nomodeline

## Useful Websites

- [Khadas Docs on VIM1s](https://docs.khadas.com/products/sbc/vim1s/start)
- [Khadas Site](https://www.khadas.com/vim1s)
- [VIM1S Community](https://forum.khadas.com/c/khadas-vim1s/42)


## Debian Image specific

Reboot / Shutdown: systemctl reboot or systemctl shutdown


### Network Interface
@code
nmcli dev wifi rescan
nmcli dev wifi list
nmcli dev wifi connect "SSIDNAMEHERE" password "SECRETHERE"
ip addr show
@end

Alternatively
/bin/nano /etc/network/interfaces
Add:
@code
# my wifi device
allow-hotplug wlp2s0
iface wlp2s0 inet dhcp
    wpa-ssid ESSID
    wpa-psk PASSWORD
@end

## Configurations

Control the LED behavior by running this command with one of these triggers.
ex: turn off the LED
echo none |sudo tee /sys/class/leds/pwmled/trigger
values: none; default-on; heartbeat


