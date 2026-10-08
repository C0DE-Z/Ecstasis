
`BIG_MUFF_audio.cir` is an ngspice testbench transcribed from the audio
components and connections in `BIG_MUFF.kicad_sch`. It includes the four
BC547 gain stages, both antiparallel clipping pairs, the tone network, and
the sustain, tone, and volume controls.

## Run

Install ngspice, then run this from the project directory:

```text
ngspice -b BIG_MUFF_audio.cir
```

The deck writes `BIG_MUFF_ac.csv` (20 Hz–20 kHz response and gain),
`BIG_MUFF_stages.csv` (individual stage gains), and
`BIG_MUFF_nodes.csv` (AC node levels), and `BIG_MUFF_transient.csv` (50 ms at
1 kHz) to the current directory. To inspect the curves interactively, open the
deck in ngspice and use:

```text
source BIG_MUFF_audio.cir
```

The default transient input is a 25 mV peak, 1 kHz sine wave with 10 kOhm
source resistance; adjust `INPUT_PEAK` to test other pickup levels. The AC
analysis uses a 1 V small-signal source. Pot positions are parameters from 0
to 1 near the top of the deck: `SUSTAIN`, `TONE`, and `VOLUME`.

