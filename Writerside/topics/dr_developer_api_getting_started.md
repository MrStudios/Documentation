# Getting Started
In this document, you will find how to add ``deathrun-api`` to your project.

### Repository
To add our repository to your build system, you must add lines described bellow to your build system file.

- Maven
```xml
<repository>
    <id>mrstudios-public</id>
    <url>https://repo.mrstudios.pl/public</url>
</repository>
```

- Gradle (Groovy)
```Groovy
maven {
    name "mrstudios-public"
    url "https://repo.mrstudios.pl/public"
}
```

- Gradle (Kotlin)
```Kotlin
maven {
    name = "mrstudios-public"
    url = uri("https://repo.mrstudios.pl/public")
}
```

### Dependency
To add ``deathrun-api`` to your project, you must add lines described bellow to your build system file.

- Maven
```xml
<dependency>
    <groupId>pl.mrstudios.deathrun</groupId>
    <artifactId>deathrun-api</artifactId>
    <version>VERSION</version>
    <scope>provided</scope>
</dependency>
```

- Gradle (Groovy)
```Groovy
implementation "pl.mrstudios.deathrun:deathrun-api:VERSION"
```

- Gradle (Kotlin)
```Kotlin
implementation("pl.mrstudios.deathrun:deathrun-api:VERSION")
```