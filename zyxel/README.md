# Info

In this directory you have to copy the WiMoVE package you want to install on the zyxel APs. Additionally you have to place a file called `conf-ota.j2`. You can generate such a file by executing `uci export` on the AP and copying the contents.

Then adjust the `wifi-iface` section that it contains the following lines:

```text
option ssid '{{ ssid }}'
option isolate '1'
option key '{{ secret }}'
option ieee80211r '{{ fast_transition }}'
option mobility_domain '0101'
option reassociation_deadline '1000'
option ft_over_ds '{{ ft_over_ds }}'
option ft_psk_generate_local '1'
option per_sta_vif '1'
option vlan_file '/etc/hostapd.vlan'
```

This will ensure that the Wi-Fi is properly configured.
