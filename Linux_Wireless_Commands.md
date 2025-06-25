### Rename Interface

```bash
sudo ip link set wlx123abc name panda0

## Permanent (Udev):

sudo nano /etc/udev/rules.d/70-custom-net-names.rules

### Add this:

SUBSYSTEM=="net", ACTION=="add", ATTR{address}=="XX:XX:XX:XX:XX:XX", NAME="panda0"
```

Replace MAC with the one from:

```bash
ip link show
```

Then:

```bash
sudo udevadm control --reload
sudo udevadm trigger
```

### Set Monitor Mode

```bash
sudo ip link set panda0 down
sudo iw panda0 set monitor control
sudo ip link set panda0 up

## To revert:

sudo ip link set panda0 down
sudo iw panda0 set type managed
sudo ip link set panda0 up

## Verify

iw dev panda0 info ### Must see "type monitor"
```

### Injection Support

Install `aircrack-ng`:

```bash
sudo dnf install aircrack-ng
```

Then:

```bash
sudo aireplay-ng --test panda0
```

This will _test packet injection_. Output should say:

```
Injection is working!
```

### Some Useful commands

```
lsusb # See if it's plugged in, you should see something like Ralink Technology, Corp. RT5572 ...

iw dev # See if it's detected 

sudo iw list | grep monitor # Check if monitor mode is supported 

iwconfig # Check current mode 

sudo aireplay-ng --test wlan0 # Test for injection
```
