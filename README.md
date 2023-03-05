# md2json action

[![Lint code base][1]][2]
[![Update release tags][3]][4]
[![Add issues to project][5]][6]

[1]: <https://github.com/bewuethr/md2json-action/actions/workflows/lint.yml/badge.svg>
[2]: <https://github.com/bewuethr/md2json-action/actions/workflows/lint.yml>
[3]: <https://github.com/bewuethr/md2json-action/actions/workflows/releasetracker.yml/badge.svg>
[4]: <https://github.com/bewuethr/md2json-action/actions/workflows/releasetracker.yml>
[5]: <https://github.com/bewuethr/md2json-action/actions/workflows/addtoproject.yml/badge.svg>
[6]: <https://github.com/bewuethr/md2json-action/actions/workflows/addtoproject.yml>

An action to convert Markdown to JSON

## Inputs

### `markdown`

**Required** A string containing the Markdown to be converted.

## Outputs

### `json`

An escaped one-line string containing the JSON syntax tree for the provided
Markdown input; use `fromJSON` to convert back to JSON

## Example usage

```yaml
- name: Convert Markdown to JSON
  uses: bewuethr/md2json-action@v0
  id: convert
  with:
    markdown: |
      # The title

      This is example Markdown input.

- name: Print output
  env:
    json: ${{ fromJSON(steps.convert.outputs.json) }}
  run: |
    jq . <<< "$json"
```
