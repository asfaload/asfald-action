# asfald-action

Installs `asfald` so you can more safely download github releases artifacts.

`asfald` will validate the checksums of downloaded files against checksums files published by the project as well as the checksums files mirrored on another server.
This increase your confidence that the files were not tampered with.

```yaml
name: Asfald Action Demo
run-name: ${{ github.actor }} is using asfald 🚀
on:
  workflow_dispatch:
jobs:
  test-asfaload:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/asfald-action@v0.1.0
      - run: |
          asfald https://github.com/superfly/flyctl/releases/download/v0.3.48/flyctl_0.3.48_Linux_x86_64.tar.gz
```
```
