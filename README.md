# version-retriever

![](https://img.shields.io/github/v/tag/CarterChen247/version-retriever?label=version)

This Github Action help you retrieve the version from the branch you pushed.

if the name of the pushed branch is `release/1.0.0`, you'll get `1.0.0` by using this action.

see [this job](https://github.com/CarterChen247/version-retriever/runs/1271284436?check_suite_focus=true) for more information.

## Inputs

This action does not require inputs. Every time when you pushed a branch, it will retrieve the version automatically.

## Outputs

### `version`

the version part retrieved from the pushed branch.

## Example usage

```
uses: CarterChen247/version-retriever@v1
```
you can print the retrieved version by `echo ${{ steps.version-retriever.outputs.version }}`

see [main.yml](https://github.com/CarterChen247/version-retriever/blob/main/.github/workflows/main.yml) for more detailed usage.

## Failed Gracefully

Every time when you push a branch, this action will perofrm a version format check. If the version retrieved by this action is not a valid version, will call `exit 1` and stops the entire workflow. See [this job](https://github.com/CarterChen247/version-retriever/runs/1271292635?check_suite_focus=true) for this scenario.
