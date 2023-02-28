# Template for a composite action

[![Lint code base][1]][2]
[![Update release tags][3]][4]
[![Add issues to project][5]][6]

[1]: <https://github.com/bewuethr/composite-action-template/actions/workflows/lint.yml/badge.svg>
[2]: <https://github.com/bewuethr/composite-action-template/actions/workflows/lint.yml>
[3]: <https://github.com/bewuethr/composite-action-template/actions/workflows/releasetracker.yml/badge.svg>
[4]: <https://github.com/bewuethr/composite-action-template/actions/workflows/releasetracker.yml>
[5]: <https://github.com/bewuethr/composite-action-template/actions/workflows/addtoproject.yml/badge.svg>
[6]: <https://github.com/bewuethr/composite-action-template/actions/workflows/addtoproject.yml>

This is a template for a composite action running a stand-alone Bash script.

## Inputs

### `required-input`

**Required** Description of the input.

### `optional-input`

**Optional** Description of optional input; defaults to `<value>`.

## Outputs

### `output`

Description of output.

## Example usage

```yaml
- name: A meaningful step name
  uses: bewuethr/<action-name>@v1
  id: id
  with:
    required-input: something

- name: Print output
  env:
    value: ${{ steps.id.outputs.output }}
  run: |
    echo "Output: $value"
```
