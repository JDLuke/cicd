# JDs CI/CD Pipelines

Build pipelines 

A set of workflow pipelines for CI/CD in Github.

## Roadmap
MVP 1 will be primarily concerned with building Java projects using maven. It will define the general lifecycle
to be used by all projects. Some goals will include:
- Build a single artifact to be stored and used throughout the pipeline. If all tests pass, that is the artifact which will be released unchanged.
- Fail fast - All tests are run as soon as possible, and in parallel when we can.
- Be opinionated. Yes, unit tests are required, no, I'm not providing a work-around.
- Be professional. Support a variety of industry-standard tools and processes
- Be extensible.
- Be usable.

After I'm satisfied with the overall flow with a single set of tools, I'll look at branching out. Most likely I'll start with adding gradle as a selectable build tool.

- [Quick How-to](docs/Howto.md)
- [Configuration](docs/Configuration.md)
- [Inspiration](docs/Inspiration.md)

