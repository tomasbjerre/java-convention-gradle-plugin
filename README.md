# Java Convention Gradle Plugin

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/se.bjurr.gradle.java-convention/se.bjurr.gradle.java-convention.gradle.plugin/badge.svg)](https://search.maven.org/artifact/se.bjurr.gradle.java-convention/se.bjurr.gradle.java-convention.gradle.plugin)

Defines the Java conventions I use in my projects.

- Code formatting
- Static code analysis, tools and configuration
- Annotation processing, code generation folders
- Plugins, which ones and configuration
- JVM Args

## Usage

Apply it with:

```groovy
plugins {
 id "se.bjurr.gradle.java-convention" version "X"
}
```

It can be tweaked in `gradle.properties` with some properties, the plugin reads them like this:

```groovy
// ---- default config ----
// mainClass: se.bjurr.violations.main.Main
mainClass: project.getProperties().getOrDefault("mainClass", ""),
sourceCompatibility: project.getProperties().getOrDefault("sourceCompatibility", "17"),
targetCompatibility: project.getProperties().getOrDefault("targetCompatibility", "17"),
maxViolations: Integer.parseInt(project.getProperties().getOrDefault("maxViolations", "0")),
formattingExcludedPatterns: project.getProperties().getOrDefault("formattingExcludedPatterns", "**/gen/**,**/generated/**"),
generatedSourceFolders: project.getProperties().getOrDefault("generatedSourceFolders", "src/gen/java,src/generated/java"),
extraTestSourceFolders: project.getProperties().getOrDefault("extraTestSourceFolders", "src/test/generated"),
jarResourcesFolder: project.getProperties().getOrDefault("jarResourcesFolder", "src/jar/resources"),
useViolations: project.getProperties().getOrDefault("useViolations", "true") == "true",
// ---- default config ----
```

Works great with https://github.com/tomasbjerre/conventional-release-gradle-plugin
