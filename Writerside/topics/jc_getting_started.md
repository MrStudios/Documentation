# Getting Started
In this document, you will find how to add `mrstudios-public` repository to your project, and you will find requirements.

### Requirements
- Java 17
- Maven or Gradle

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