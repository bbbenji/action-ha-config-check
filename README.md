# HA-CONFIG-CHECK

_Check Home Assistant Configuration_

## Example

```
on: push
name: Check Home Assistant Configuration
jobs:
  build:
    name: DEV
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: DEV
      uses: bbbenji/action-ha-config-check@master
      env:
        ACTION_ALLOW_FAIL: "True"
        ACTION_VERSION: DEV
    - name: RC
      uses: bbbenji/action-ha-config-check@master
      env:
        ACTION_VERSION: RC
    - name: STABLE
      uses: bbbenji/action-ha-config-check@master
      env:
        ACTION_VERSION: STABLE
```

**REQUIRE GITHUB_TOKEN**

## ENV VARS

ENV | description
-- | --
`ACTION_VERSION` | `STABLE`, `RC` or `DEV`.
`ACTION_CONFIG_PATH` | Relative path to your configuration if not in the root of the repository.
`ACTION_ALLOW_FAIL` | Set to `True` to allow failure.