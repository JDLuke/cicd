# How to use the pipelines

1. In your project root, create a .github/workflows directory
2. Add a .yml file triggered by your desired event to the workflows directory. For this example, we will use a 'push' event to the branch 'main'.  This will be kicked off either by direct push or by merges. See: [sample](call-pipeline.yml)
3. \(Optional\) Add a config.yml file to the root of your project containing any configuration values you wish to override.

TODO - List out configuration values and their effects on pipeline
