# The engine: a closed cycle over reservoirs

**Live page:** https://ianpilon.github.io/reservoir-memory-demo/

An interactive essay on the reservoir-computing model of memory, with a real echo state network running live in the browser. Field Notes Vol. II, following [spreading-activation-demo](https://github.com/ianpilon/spreading-activation-demo) (Vol. I).

## The model

A 90-unit reservoir with fixed sparse random recurrent weights (scaled near the edge of stability), leaky tanh units, and a single linear readout trained continuously by an online least-squares rule. A drifting world signal, mixed with a distractor and noise, streams in. The readout weights are the only thing that ever learns; everything else just ripples.

The core claims of the model, each runnable as an experiment:

1. **Consolidation trains it; reconstruction runs it.** The same readout, two modes. Training never stops, because the world never stops drifting.
2. **There is no single store being written.** The memory lives in the joint state of every unit at once.
3. **The loop is what makes it memory.** Reconstruction feeds action, action changes the world, the world feeds the stream, and the self re-gates the next pass.

## The experiments

- **Wipe the readout** — the reservoir keeps rippling, yet reconstruction collapses. The ripples alone are not the memory; consolidation retrains the readout from scratch in seconds.
- **Pause consolidation** — reconstruction keeps running, then decays as the world drifts. There is no "done" state for memory.
- **Close the self-gate** — the stream fills with distractor and the readout tunes to the wrong world. Gating selects which world you end up remembering.
- **Sever the loop** — action stops stabilizing the world, the world wanders and lurches, and memory degrades into a recording device pointed at chaos.

## Vol. III — A recording is a loop, cut open

**Live page:** https://ianpilon.github.io/reservoir-memory-demo/contrast.html

A companion essay (`contrast.html`) that teaches the loop claim by contrast, in two moves:

1. **One arrow apart.** An animated diagram that cuts the six-station ring and unrolls it into a flat pipeline. The return arrow dangles into nothing, and the self fades out with its spokes: a pipeline has no hub for a self to occupy.
2. **The twin experiment.** The same live reservoir, with a "cut" button that clones the memory's readout and freezes the copy. Memory and recording are identical at the instant of the cut, then part company as the world drifts. The divergence wedge between their error curves is the argument.

Both pages carry a shared series nav linking Vol. I ([spreading-activation-demo](https://ianpilon.github.io/spreading-activation-demo/)), Vol. II (`index.html`), and Vol. III (`contrast.html`).

Each page is one self-contained HTML file: inline CSS, canvas simulation, and SVG, no external assets. Companion to [memory-living-loop](https://github.com/ianpilon/memory-living-loop).
