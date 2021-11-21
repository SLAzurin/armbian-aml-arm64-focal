# armbian-aml-arm64-focal
Mirror for the latest build of Armbian for Amlogic arm64 SoCs (Ubuntu Focal) Built by @150balbes

## Known issues:

"sudo" breaks after a while.

Solution by migg:
```bash
  chown root:root /usr/bin/sudo 
  chmod 4755 /usr/bin/sudo
  chown root:root /usr/lib/sudo/sudoers.so 
  chmod 4755 /usr/lib/sudo/sudoers.so
  chown root:root /etc/sudoers
  chown root:root /etc/sudoers.d /etc/sudoers.d/README  /var/lib/sudo
```
Or keep using sudo only through ctrl + alt + f3 / ssh

Ref: https://forum.armbian.com/topic/8288-how-to-fixsurvive-a-broken-sudo/?tab=comments#comment-62588


## Known issues 2:

Wifi fix for AP6330

Solution by ZuiMelanieForno:
```bash
  sudo mv /lib/firmware/brcm/brcmfmac4330-sdio.txt /lib/firmware/brcm/brcmfmac4330-sdio.txt.old
  sudo ln -s  /lib/firmware/brcm/brcmfmac-ap6330-sdio.txt /lib/firmware/brcm/brcmfmac4330-sdio.txt
```

Ref: https://forum.armbian.com/topic/13520-armbian-build-for-nexbox-a95x-with-ap6330/