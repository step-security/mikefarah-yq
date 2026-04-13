[![StepSecurity Maintained Action](https://raw.githubusercontent.com/step-security/maintained-actions-assets/main/assets/maintained-action-banner.png)](https://docs.stepsecurity.io/actions/stepsecurity-maintained-actions)

# yq - GitHub Action

A GitHub Action that provides [yq](https://github.com/mikefarah/yq), a lightweight and portable command-line YAML, JSON, INI and XML processor. `yq` uses [jq](https://github.com/stedolan/jq)-like syntax but works with yaml files as well as json, xml, ini, properties, csv and tsv.

## Usage

```yaml
  - name: Set foobar to cool
    uses: step-security/mikefarah-yq@v4
    with:
      cmd: yq -i '.foo.bar = "cool"' 'config.yml'
  - name: Get an entry with a variable that might contain dots or spaces
    id: get_username
    uses: step-security/mikefarah-yq@v4
    with:
      cmd: yq '.all.children.["${{ matrix.ip_address }}"].username' ops/inventories/production.yml
  - name: Reuse a variable obtained in another step
    run: echo ${{ steps.get_username.outputs.result }}
```

## Inputs

| Input | Description | Required |
|-------|-------------|----------|
| `cmd` | The yq command to run | Yes |

## Outputs

| Output | Description |
|--------|-------------|
| `result` | The complete result from the yq command being run |

See [yq documentation](https://mikefarah.gitbook.io/yq/) for detailed usage of the yq tool itself.
