# Operit Avatar Assets

Curated avatar presets for the Operit fork. The app reads `presets.json` from
this repository and downloads a model only when the user picks it.

Layout:

    presets.json
    presets/
      gltf/<id>/model.glb
      gltf/<id>/LICENSE.txt
      dragonbones/<id>/...
      webp/<id>/...
      mp4/<id>/...
      mmd/<id>/...

`presets.json` is the single source of truth: every entry carries `type`,
`model` path, `sha256`, `sizeBytes`, `license`, `licenseFile`, and the
animation names the app should map to moods.

Rules for new presets:

- keep the model file self-contained (.glb preferred) and avoid required glTF
  extensions the Android renderer does not load;
- add a `LICENSE.txt` next to the model and record its licence in the catalog;
- update `sha256` and `sizeBytes` whenever the model changes;
- do not include content whose terms forbid redistributing it.

The `xbot` and `soldier` entries come from the three.js example bundle and are
Mixamo exports. They are convenient for demos, but their terms should be
reviewed before wider redistribution.
