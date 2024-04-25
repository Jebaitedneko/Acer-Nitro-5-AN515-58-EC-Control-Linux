# Acer-Nitro-5-AN515-58-EC-Control-Linux

Implementation of basic EC registers that NitroSense Modifies, as a Bash Script

The script also restores Keyboard RGB Profile set in Windows

Along with setting PL1 and PL2 limits via MSR and MCHBAR

# Requirements

Kernel Commandline (/etc/default/grub)

```
ec_sys.write_support=1 msr.allow_writes=on
```

`ec_sys` present in your kernel modules or at `~`

Find it on your current kernel with

```
find /lib/modules -type f -iname "*ec_sys.ko*"
```

# Usage

To show available switches

```
sudo bash nitrosense
```

Available Switches

```
ENA: [w]rite to ec
PWR: [q]uiet [d]efault [p]erformance
FAN: [a]uto  [c]ustom  [m]ax
DBG: [r]ead from ec
DBG: [e]nergy data from intel_rapl
DBG: [n]vidia-powerd restart
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

The script also sets a default PL1 and PL2 limit of 75w

Along with PL1 and PL2 Timing of 1 minute

To dump current EC registers

```
sudo bash nitrosense x
```
