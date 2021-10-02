# The SPICE model file reducer

This Python script traverses through a SPICE model file, removes empty lines and comments, and extracts the
given section (default is `tt`). It further produces a flat singel model file for use with e.g. `ngspice`.

**Usage:**

```
spice_model_red.py input_file [section]
```

It reads the `input_file` and writes an output file called `input_file.<section>.red`.

**Todo:**

* TESTING!!!
* Add fail saves around file operations
* Add better control of output during run, maybe add a `-v` switch
