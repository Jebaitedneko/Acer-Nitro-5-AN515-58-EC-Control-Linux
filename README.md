# Acer-Nitro-5-AN515-58-EC-Control-Linux

Implementation of basic EC registers that NitroSense Modifies, as a Bash Script

# Requirements

Kernel Commandline (/etc/default/grub)

```
ec_sys.write_support=1 msr.allow_writes=on
```

The `ec_sys.ko` module to be present at `~`

Find it on your current kernel with

```
find /lib/modules -type f -iname "*ec_sys.ko*"
```

Copy the .ko file over to `~` as `ec_sys.ko`

```
find /lib/modules -type f -iname "ec_sys.ko" -exec cp {} ~ \;
```

# Usage

To show available switches

```
sudo bash nitrosense
```

Available Switches

```
PWR:  [q]uiet [d]efault [p]erformance
FAN:  [a]uto  [c]ustom  [m]ax
DBG: e[x]tract ec
```

Example: Default Power with Auto Fan

```
sudo bash nitrosense da
```

Example: Performance Power with Max Fan

```
sudo bash nitrosense pm
```

Example: Performance Power with Custom Fan at 50%

```
sudo bash nitrosense pc 50
```

# Notes

The script also sets a default PL1 and PL2 limit of 95w

Along with PL1 and PL2 Timing of 1 minute

To dump current EC registers

```
sudo bash nitrosense x
```
