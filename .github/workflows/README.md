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
    uses: tooppoo/release-workflows/.github/workflows/_setup_artifacts.yml@main
    with:
      config_path: .github/release-artifacts.json
```

## wf-installer-smake-test.yml

```yml
name: CI

on:
  push:
    tags:
      - "v*"

permissions:
  contents: read

jobs:
  installer-smoke-test:
　  uses: tooppoo/github-release-workflows/.github/workflows/wf-installer-smoke-test.yml@main
    with:
      config_path: .github/workflows/artifacts.manifest.json
```
