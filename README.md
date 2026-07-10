# The engine: a closed cycle over reservoirs

**Live page:** https://ianpilon.github.io/memory-field-notes/

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

**Live page:** https://ianpilon.github.io/memory-field-notes/contrast.html

A companion essay (`contrast.html`) that teaches the loop claim by contrast, in two moves:

1. **One arrow apart.** An animated diagram that cuts the six-station ring and unrolls it into a flat pipeline. The return arrow dangles into nothing, and the self fades out with its spokes: a pipeline has no hub for a self to occupy.
2. **The twin experiment.** The same live reservoir, with a "cut" button that clones the memory's readout and freezes the copy. Memory and recording are identical at the instant of the cut, then part company as the world drifts. The divergence wedge between their error curves is the argument.

## Vol. IV — Every recall reopens the write

**Live page:** https://ianpilon.github.io/memory-field-notes/reconsolidation.html

Vol. III conceded that the model didn't touch memories being reshaped by every act of recall. Vol. IV (`reconsolidation.html`) closes that gap: the same reservoir, holding a memory of a *finished* event. The world signal is gone; only a recall cue remains, so the only thing that can retrain the readout is the act of remembering itself.

- **Leave it alone** — an unrecalled memory never changes. Between recalls, a memory is a recording.
- **Retell it** — each retelling reconsolidates toward a schematized copy of the last telling. Detail washes out ~30% per retelling while gist holds. Bartlett's (1932) serial reproduction, run on weights.
- **Ask a leading question** — a suggestion mixed into one recall gets written in, then carried forward by later innocent retellings as if it had always been there. The Loftus misinformation effect, live.
- **Relive the event** — the only undo, and the punchline: real past events have no relive button. Vol. II's distortions healed in seconds because the world was still streaming in; a finished event has no world left to appeal to.

Gist / detail / intrusion meters are scored against an offstage copy of the original event that the network (like a real rememberer) has no access to.

All four volumes live in this repo and carry a shared series nav: Vol. I (`activation.html`, a copy of [spreading-activation-demo](https://github.com/ianpilon/spreading-activation-demo)), Vol. II (`index.html`), Vol. III (`contrast.html`), and Vol. IV (`reconsolidation.html`), so you can move between volumes without leaving the site.

Each page is one self-contained HTML file: inline CSS, canvas simulation, and SVG, no external assets. Companion to [memory-living-loop](https://github.com/ianpilon/memory-living-loop).
