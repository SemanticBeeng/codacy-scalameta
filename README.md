[![Codacy Badge](https://api.codacy.com/project/badge/grade/448773a482094001a1104979ca00350c)](https://www.codacy.com)

# Codacy scala.meta

This is the codacy engine for scala static code analysis build on top of scala.meta.
Check the **Docs** section for more information.

## Developing

### Quasiquotes:
https://github.com/scalameta/scalameta/bob/master/notes/quasiquotes.md

### Tool Integration:
http://docs.codacy.com/v1.5/docs/tool-developer-guide

### Testing with "sbt console":

import scala.meta._

val code = """ .... """

val tree = code.parse[Source]

codacy.patterns.Custom_Scala_ElseIf(tree)

//To see the tree structure:

tree.show[Structure]

## Usage

You can create the docker by doing:

```
sbt docker:publishLocal
```

The docker is ran with the following command:

```
docker run -it -v $srcDir:/src  <DOCKER_NAME>:<DOCKER_VERSION>
```

## Docs

[Tool Developer Guide](http://docs.codacy.com/v1.5/docs/tool-developer-guide)

[Tool Developer Guide - Using Scala](http://docs.codacy.com/v1.5/docs/tool-developer-guide-using-scala)

## Test

We use the [codacy-plugins-test](https://github.com/codacy/codacy-plugins-test) to test our external tools integration.
You can follow the instructions there to make sure your tool is working as expected.