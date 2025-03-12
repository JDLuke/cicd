I want this thing to run if you don't configure it.

That may not be possible once I extend the product sufficiently, of course.

But for now, if you've got a valid maven or gradle project, you ought to be able to get a tested and deployed build. Note: We do not yet support auto-versioning of gradle projects.

That being said, we do support a configuration file to control the build. It must be named config.yml \(that will probably change, it's too generic.\) and must be in the root directory of the project.

For now there are only a few valid keys. Details can be found in [How-to](Howto.md#configuration-values)


Example config.yml:

    dependency_tests: false
    component_tests: false
    bump_version: false
    create_release: false
