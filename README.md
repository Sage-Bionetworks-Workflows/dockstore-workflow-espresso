# dockstore-workflow-espresso
A WDL workflow for WGS data processing

# Description
The WDL workflow that is published in this repository was initially generated using the [espresso-caller](https://pypi.org/project/espresso-caller/) Python tool, which is published under the [MIT license](https://opensource.org/licenses/MIT)

## WDL

The main workflow file, `haplotype-calling.wdl` is placed at the root of the
repository. Subworkflows are present in the `subworkflows` folder. 

## Tests

[`pytest-workflow`](https://pytest-workflow.readthedocs.io/en/stable/) is used for
testing. To use, create a YAML file in the `tests` directory that starts with `test`. 
For more information, see the [tests README](tests/TEST_README.md).
