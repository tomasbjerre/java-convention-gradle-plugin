# Java Convention Gradle Pluigin

Defines the Java conventions I use in my projects.

- Code formatting
- Static code analysis, tools and configuration
- Annotation processing, code generation folders
- Plugins, which ones and configuration
- JVM Args

```groovy
plugins {
    id 'se.bjurr.gradle.java-convention' version 'X'
}
```

<https://plugins.gradle.org/plugin/se.bjurr.gradle.java-convention>

It can be tweaked in `gradle.properties` with some properties:

<!-- start default config -->
```groovy

def givenConfig = [
	// mainClass: se.bjurr.violations.main.Main
	mainClass: gradleProps.getProperty("mainClass", ""),
	sourceCompatibility: gradleProps.getProperty("sourceCompatibility", "17"),
	targetCompatibility: gradleProps.getProperty("targetCompatibility", "17"),
	maxViolations: gradleProps.getProperty("maxViolations", "0"),
	formattingExcludedPatterns: gradleProps.getProperty("formattingExcludedPatterns", "**/gen/**,**/generated/**"),
	generatedSourceFolders: gradleProps.getProperty("generatedSourceFolders", "src/gen/java,src/generated/java"),
	extraTestSourceFolders: gradleProps.getProperty("extraTestSourceFolders", "src/test/generated"),
	jarResourcesFolder: gradleProps.getProperty("jarResourcesFolder", "src/jar/resources"),
]

```
<!-- end default config -->
