# Setup
In this document, you will find how to add `commons-inject` in your project.

### Dependency
To add ``commons-inject`` to your project, you must add lines described bellow to your build system file.

- Maven
```xml
<dependency>
    <groupId>pl.mrstudios.commons</groupId>
    <artifactId>commons-inject</artifactId>
    <version>VERSION</version>
    <scope>provided</scope>
</dependency>
```

- Gradle (Groovy)
```Groovy
implementation "pl.mrstudios.commons:commons-inject:VERSION"
```

- Gradle (Kotlin)
```Kotlin
implementation("pl.mrstudios.commons:commons-inject:VERSION")
```