# github-release-workflows

## wf-cross-platform-build.yml

```yml
name: release

on:
  push:
    tags:
      - "v*"

permissions:
  contents: read
  actions: write

jobs:
  setup-artifacts:
    uses: tooppoo/release-workflows/.github/workflows/_setup_artifacts.yml@v1
    with:
      config_path: .github/release-artifacts.json
```
