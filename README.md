# Gradle Example

Project created in order to learn a bit about Gradle and add security dependencies check.

This project was created following this [tutorial](http://www.petrikainulainen.net/getting-started-with-gradle/) with some modifications due to out-of-date informations. So check this [link](https://docs.gradle.org/current/userguide/java_plugin.html#sec:java_plugin_and_dependency_management) as well.

## Structure

I am using a java plugin for gradle `apply plugin: 'java'`.

The plugin requests the following project structure:

src

    main
        java
            package-level-1
            .
            .
            .
        resources
    test
        java

After to proceed with a clone, inside of the project's folder run `gradle test`.

To run the project use `java -jar build/libs/gradle-example.jar`.

Some interesting tasks that come with java plugin:

- **assemble**: just build the project (create a build folder with a jar file, .class files, etc) but it doesn't run tests;
- **build**: build and test the project;
- **test**: run tests.

## Security checks

### Dependencies check

**Dependency Check for Gradle**

https://jeremylong.github.io/DependencyCheck/dependency-check-gradle/

Run the command `gradle dependencyCheck`. Check out [this](https://jeremylong.github.io/DependencyCheck/dependency-check-gradle/index.html) to more info.

**Adding exceptions to false positives**

You have to add in your build.gradle file the following lines:

```
dependencyCheck {
    suppressionFile=FILE-PATH
}
```

Where FILE-PATH is a string with the path to your xml file. More information [here](https://jeremylong.github.io/DependencyCheck/general/suppression.html).

## Helpful links

https://docs.gradle.org/current/userguide/organizing_build_logic.html

https://www.owasp.org/index.php/OWASP_Dependency_Check