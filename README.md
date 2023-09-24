# Acer-Nitro-5-AN515-58-EC-Control-Linux

Implementation of basic EC registers that NitroSense Modifies, as a Bash Script

The script also restores Keyboard RGB Profile set in Windows

Along with setting PL1 and PL2 limits via MSR and MCHBAR

Support running under secure boot mode or a lockdowned kernel with the help of [acpi_ec](https://github.com/MusiKid/acpi_ec)

# Requirements

1. Install the kernel module `acpi_ec` according to the instructions [here](https://github.com/MusiKid/acpi_ec?tab=readme-ov-file#installation).
2. Reboot.

# Usage

To show available switches

```
./nitrosense
```

Available Switches

```
PWR: [q]uiet [d]efault [p]erformance
FAN: [a]uto  [c]ustom  [m]ax
DBG: [r]ead from ec
DBG: [e]nergy data from intel_rapl
DBG: [n]vidia-powerd restart
```

Example: Default Power with Auto Fan

```
./nitrosense da
```

Example: Performance Power with Max Fan

```
./nitrosense pm
```

Example: Performance Power with Custom Fan at 50%

```
./nitrosense pc 50
```

# Notes

The script also sets a default PL1 and PL2 limit of 95w

Along with PL1 and PL2 Timing of 1 minute

To dump current EC registers

```
./nitrosense r
```
