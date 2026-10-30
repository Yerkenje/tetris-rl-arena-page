# Tetris RL Arena — public project page

Static public site for the ISSAI FRP 2026 project **Tetris RL Arena: Afterstate
Reinforcement Learning under Execution Noise** by Erkenzhe.

The site is plain HTML, CSS and JavaScript. It has no build step, no model calls,
no analytics and no external libraries.

## Pages

- `index.html` — project overview, verified Study 1 and Study 2 results, figures,
  limitations, AI-assistance disclosure and citation.
- `replay.html` — interactive viewer for recorded JSON simulations, with three
  comparison presets, playback and seek controls, noise-error navigation and
  manual JSON upload. This is replay, not live neural-network inference.
- `paper.html` — verified abstract and result summary. A compiled PDF is not
  included; `paper/tetris-paper-overleaf.zip` is the public-safe LaTeX source.

## Local preview

From this folder:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000/`. The workspace preview is:

```bash
frp-serve 8000
```

## Replays

`replays/` contains six short demonstration clips copied from the final verified
run:

| Preset | Left | Right |
| --- | --- | --- |
| Original vs Combo, 0% noise | `rl1_seed5000_noise00.json` | `combo_seed5000_noise00.json` |
| Lines, clean vs noise-trained, 10% noise | `lines_clean_seed6000_noise10.json` | `lines_noise10_seed6000_noise10.json` |
| Combo, clean vs noise-trained, 10% noise | `combo_clean_seed6000_noise10.json` | `combo_noise10_seed6000_noise10.json` |

The clips are not the 2,000-piece evaluation games, so their scores are not the
paper's means.

## Provenance

The reported numbers correspond to the final verified results at commit
`bf75e7c` of the private research repository. This public repository does not
contain training code, checkpoints, raw logs or the research repository history.

The research repository is private. The public project page is:
https://yerkenje.github.io/tetris-rl-arena-page/

## Compile the paper source

Unzip `paper/tetris-paper-overleaf.zip` and run:

```bash
pdflatex main
bibtex main
pdflatex main
pdflatex main
```

The package was assembled without a TeX engine on the build machine, so no
compiled PDF is included.
