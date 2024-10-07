# How to use the pipelines

## Setting up a pipeline.yml

Let's take a look at how to call the pipeline you wish to use. We'll break down the sample file a bit.

    name: Pipeline

First, we define the name we want for this pipeline. This is mainly for reporting purposes.

    on:
      push:  # Run tests on all branches
        branches: ["**"]
      pull_request:  # Run tests on PRs targeting any branch
        branches: ["**"]

Now we tell Github when we want the pipeline to run. There are a lot of options for this, but in this case we're just
going to run the pipeline anytime we push to any branch as well as any time a pull request is opened for any branch.

    permissions:
    contents: write
    deployments: write

The permissions are required in order to allow your pipeline invocation to take certain privileged actions, such as
updating your repository or creating binary deployments.

    jobs:
      run-pipeline:
        uses: JDLuke/cicd/.github/workflows/pipeline.yml@main

Finally, we invoke the actual pipeline we want to run. The name (in this case, 'run-pipeline') is arbitrary. The 'uses'
clause is not, and you need to use this exact syntax. The 'main' part will execute against whatever github currently has
as the main branch, but as this develops there will be stable version tags added to help everyone retain their sanity.

### Maven project configuration

1. In your project root, create a .github/workflows directory
2. Add a .yml file triggered by your desired event to the workflows directory. For this example, we will use a 'push'
   event to the branch 'main'. This will be kicked off either by direct push or by merges to that branch.
   See: [sample pipeline file](call-pipeline.yml), [* Note on branches](#branches)
3. \(Optional\) Add a config.yml file to the root of your project containing any configuration values you wish to
   override.

TODO - List out configuration values and their effects on pipeline

## Configuration Values

| *Key*             | *Default Value* | *Required* | *Description*                                                                                                 |
|:------------------|:----------------|:-----------|:--------------------------------------------------------------------------------------------------------------|
| java_version      | 17              | Yes        | JDK release level                                                                                             |
| java_distribution | temurin         | Yes        | JDK name                                                                                                      |
| java_cache        | maven           | Yes        | Cache strategy for Java code                                                                                  |
| bump_version      | false           | No         | Determines whether or not a successful release candidate will lead to updating the pom.xml with a new version |
| component_tests   | false           | No         | Disables component testing when set to anything but false                                                     |
| create_release    | false           | No         | Disables release creation when set to anything but false                                                      |
| dependency_tests  | false           | No         | Disable dependency testing when set to anything but false                                                     |
| PROJECT_NAME      | micronaut-guide | No         | Lets you name your project. The default is the repository name                                                |

## Branches

There is at least one explicit reference to the branch name 'main' within these hallowed halls, so if your main branch
is still called master you probably want to change that.