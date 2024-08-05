# Getting Started
In this document, you will find how to add `mrstudios-public` repository to your project, and you will find requirements.

### Requirements
- Java 17
- Maven or Gradle

### Repository
To add our repository to your build system, you must add lines described bellow to your build system file.

<tabs group="build-systems">

<tab title="Maven" group-key="maven">
    <code-block lang="xml">
        &#x3C;repository&#x3E;
            &#x3C;id&#x3E;mrstudios-public&#x3C;/id&#x3E;
            &#x3C;url&#x3E;https://repo.mrstudios.pl/public&#x3C;/url&#x3E;
        &#x3C;/repository&#x3E;
    </code-block>
</tab>

<tab title="Gradle (Groovy)" group-key="gradle-groovy">
    <code-block lang="groovy">
        maven {
            url "https://repo.mrstudios.pl/public/"
        }
    </code-block>
</tab>

<tab title="Gradle (Kotlin)" group-key="gradle-kotlin">
    <code-block lang="kotlin">
        maven("https://repo.mrstudios.pl/public/")
    </code-block>
</tab>

</tabs>