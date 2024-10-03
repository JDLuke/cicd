I want this thing to run if you don't configure it.

That may not be possible once I extend the product sufficiently, of course.

But for now, if you have a pom.xml and can pass a few mvn commands in the github ubuntu-latest environment, you ought to be able to get a deployed build.

That being said, we do support a configuration file to control the build. It must be named config.yml \(that will probably change\) and must be in the root directory of the project.

For now there are only a few valid keys. All are boolean values and effectively default to true.


Example config.yml:

    dependency_tests: false
    component_tests: false
    bump_version: false
    create_release: false
