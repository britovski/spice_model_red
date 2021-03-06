# The SPICE model file reducer

(c) 2021 Harald Pretl, Johannes Kepler University Linz

This Python script traverses through a SPICE model file, removes empty lines and comments, and extracts the
specified model corner (default is `tt`). It further produces a flat single model file for use with e.g. `ngspice`.

On my Unix machine, the time to simulation (`ngspice` start to actual simulation start) is 80sec using the
original SPICE model files from the SKY130A PDK created by open_pdks (https://github.com/RTimothyEdwards/open_pdks).
Using this model file reducer, the ngspice startup is improved to 5sec!

This script can also be used to check the original model file, as it reports warnings when include files
are not found.

**Usage:**

```
spice_model_red.py input_file [section]
```

It reads the `input_file` and writes an output file called `input_file.<section>.red`. If called without parameters
the script displays a help screen.

Exemplary use on the SKY130A model file:

```
spice_model_red.py sky130.lib.spice tt
```

**Todo:**

* Add better control of output during run, maybe add a `--verbose` switch.
