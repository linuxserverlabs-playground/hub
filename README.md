# hub (Labs)

The LinuxServer Labs hub: the static API and generated artefacts for the images in this organisation, served on
this repository's GitHub Pages. It runs the main hub's code ([linuxserver-playground/hub](https://github.com/linuxserver-playground/hub))
for this organisation, so the API, its shapes and its documentation are the main hub's. Labs leaves out the stores,
the mods index and the PRoot Apps index.

- `.github/workflows/deploy.yml` ingests every new release, publishes the data and publishes Pages from the
  `gh-pages` branch. Only the Labs control plane starts it, on its slots (at most nine an hour, when something
  changed: a release, a push here, refreshed data).
- `.github/workflows/refresh.yml` reads stars and archived flags hourly; control serves what changed at the next
  Deploy slot.
- The `data` branch holds the current data in one commit, replaced on every publish.

A change to how the hub works belongs in the main hub; this repository holds no code.
