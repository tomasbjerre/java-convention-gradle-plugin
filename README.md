# Java Convention Gradle Plugin

[![Gradle Plugin Portal](https://img.shields.io/gradle-plugin-portal/v/se.bjurr.gradle.java-convention)](https://plugins.gradle.org/plugin/se.bjurr.gradle.java-convention)

Defines the Java conventions I use in my projects.

- Code formatting
- Static code analysis, tools and configuration
- Annotation processing, code generation folders
- Plugins, which ones and configuration
- JVM Args

It can be tweaked in `gradle.properties` with some properties, the plugin reads them like this:

```groovy
// ---- default config ----
// mainClass: se.bjurr.violations.main.Main
mainClass: project.getProperties().getOrDefault("mainClass", ""),
sourceCompatibility: project.getProperties().getOrDefault("sourceCompatibility", "17"),
targetCompatibility: project.getProperties().getOrDefault("targetCompatibility", "17"),
maxViolations: project.getProperties().getOrDefault("maxViolations", "0"),
formattingExcludedPatterns: project.getProperties().getOrDefault("formattingExcludedPatterns", "**/gen/**,**/generated/**"),
generatedSourceFolders: project.getProperties().getOrDefault("generatedSourceFolders", "src/gen/java,src/generated/java"),
extraTestSourceFolders: project.getProperties().getOrDefault("extraTestSourceFolders", "src/test/generated"),
jarResourcesFolder: project.getProperties().getOrDefault("jarResourcesFolder", "src/jar/resources"),
useViolations: project.getProperties().getOrDefault("useViolations", "true") == true,
// ---- default config ----
```
