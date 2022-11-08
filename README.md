# dkms-hid-nintendo

A Nintendo HID kernel module.

For any questions or bug reports, please refer to [hid_nintendo](https://github.com/DanielOgorchock/linux).


## Installation

Install it from source with:

```
git clone https://github.com/nicman23/dkms-hid-nintendo
cd dkms-hid-nintendo

sudo dkms add .
sudo dkms build nintendo -v 3.2
sudo dkms install nintendo -v 3.2
```
## It doesn't work!

Open the terminal and type this command.

```
lsusb | grep 20d6:
```
Remember the number that comes after 20d6:.

Open hid_list.c in src/ and find the line `#define USB_DEVICE_ID_NINTENDO_PROCON   0x0002` and replace `0x0002` with that number, then build and install.

## Related projects

- [joycond](https://github.com/DanielOgorchock/joycond): A userspace daemon to
  combine joy-cons from the hid-nintendo kernel driver
- [joycond-cemuhook](https://github.com/joaorb64/joycond-cemuhook): Support for
  cemuhook's UDP protocol for joycond devices
