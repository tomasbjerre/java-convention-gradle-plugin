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
interface JavaConventionPluginExtension {
	Property<String> getMainClass()
	Property<String> getSourceCompatibility()
	Property<String> getTargetCompatibility()
	Property<String> getMaxViolations()
	ListProperty<String> getFormattingExcludedPatterns()
	ListProperty<String> getGeneratedSourceFolders()
	ListProperty<String> getExtraTestSourceFolders()
	ListProperty<String> getJarResourcesFolder()
	Property<String> getUseViolations()
}

def extension = project.extensions.create("javaConvention", JavaConventionPluginExtension)
extension.mainClass.convention("")
extension.sourceCompatibility.convention(17)
extension.targetCompatibility.convention(17)
extension.maxViolations.convention(0)
extension.formattingExcludedPatterns.convention(["**/gen/**","**/generated/**","**/generated-source/**"])
extension.generatedSourceFolders.convention(["src/gen/java","src/generated/java"])
extension.extraTestSourceFolders.convention(["src/test/generated"])
extension.jarResourcesFolder.convention(["src/jar/resources"])
extension.useViolations.convention(true)
// ---- default config ----
```

Works great with https://github.com/tomasbjerre/conventional-release-gradle-plugin
