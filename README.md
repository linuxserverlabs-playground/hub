# hub (Labs)

The LinuxServer Labs hub: the static API and generated artefacts for the images in this organisation, served on
this repository's GitHub Pages. It runs the main hub's code ([linuxserver-playground/hub](https://github.com/linuxserver-playground/hub))
for this organisation, so the API, its shapes and its documentation are the main hub's. Labs leaves out the stores,
the mods index and the PRoot Apps index.

- `.github/workflows/deploy.yml` ingests every new release, publishes the data and deploys Pages, on a release
  (`repository_dispatch image-released`), on demand and on every push here.
- `.github/workflows/refresh.yml` reads stars and archived flags hourly and asks for a Deploy when they changed.
- The `data` branch holds the current data in one commit, replaced on every publish.

A change to how the hub works belongs in the main hub; this repository holds no code.
