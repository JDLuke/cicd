# How to use the pipelines

### Maven project configuration

1. In your project root, create a .github/workflows directory
2. Add a .yml file triggered by your desired event to the workflows directory. For this example, we will use a 'push' event to the branch 'main'.  This will be kicked off either by direct push or by merges to that branch. See: [sample pipeline file](call-pipeline.yml), [* Note on branches](#branches)
3. \(Optional\) Add a config.yml file to the root of your project containing any configuration values you wish to override.

TODO - List out configuration values and their effects on pipeline

## Configuration Values

| *Key*             | *Default Value* | *Required* |
|:------------------|:----------------|:-----------|
| java_version      | 17              | Yes        |
| java_distribution | temurin         | Yes        |   
| java_cache        | maven           | Yes        |
| bump_version      | false           | No         |
| component_tests   | false           | No         |
| create_release    | false           | No         |
| dependency_tests  | false           | No         |
| PROJECT_NAME      | micronaut-guide | No         |




## Branches

There is at least one explicit reference to the branch name 'main' within these hallowed halls, so if your main branch is still called master you probably want to change that.