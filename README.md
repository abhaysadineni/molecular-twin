# MDT, the Molecular Digital Twin

Structure and temperature in. Energy and light out. Kept true by measurement. A digital twin of a single biomolecule.

Live: https://www.abhaychakra.com/p/molecular-twin/ (the earlier address `/p/new-project/` forwards here)

A browser prototype in WebGL. It runs from the cuvette down to the electrons, for 15 molecules:

- **Fluorescent proteins:** EGFP, mNeonGreen, mVenus, mTurquoise2, mTagBFP2, mOrange, mScarlet, mCherry, mKate2.
- **Small folding benchmarks:** ubiquitin, protein G B1, CI2, the engrailed homeodomain, villin HP35, spectrin SH3.

What you can do with it:

- **Conditions:** change temperature and pH.
- **Views:** switch between glass, element, structure, burial, motion, sensitivity, ensemble and photons.
- **Mutation:** click any atom to select its residue, then mutate it.
- **Simulated instrument:** measure a melting curve, or ask for the next best mutant to measure.

## What is real and what is synthetic

The page states this on every view:

- **Real:** the atomic structures, from the Protein Data Bank. The PDB identifier, method, resolution and temperature for each are in `data/molecules/index.json`. The fluorescent-protein spectra are real public data too.
- **Synthetic:** the stability parameters, mutation effects and instrument readings.

## This repository is the compiled build

This folder holds what is served on the site: the bundled JavaScript (`assets/app.*.js`, which includes three.js), the stylesheet, the data and the fonts. The original source and its build configuration were written in a separate working session and are not in this folder. To publish the readable source, add it from that session.

The build contains an optional AI assistant panel. It is off unless an API key is supplied at runtime, and **no key is included in this build**.

## Run it

```
python3 -m http.server 8000
```

Open http://localhost:8000, then try `#/twin/egfp`. It needs a browser with WebGL. GitHub Pages works from the root of the `main` branch.

## Licences

- **The project's own code:** no licence file is included, so default copyright applies.
- **three.js:** MIT (`vendor/THREE-LICENSE.txt`).
- **Fonts:** Manrope and JetBrains Mono under the SIL Open Font License 1.1 (notices in `fonts/`).
- **Structures:** Protein Data Bank archive data are released by the wwPDB under CC0 1.0.
