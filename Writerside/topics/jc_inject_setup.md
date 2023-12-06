# Setup
In this document, you will find how to add `commons-inject` in your project.

### Dependency
To add ``commons-inject`` to your project, you must add lines described bellow to your build system file.

<tabs group="build-systems">

<tab title="Maven" group-key="maven">
    <code-block lang="xml">
        &#x3C;dependency&#x3E;
            &#x3C;groupId&#x3E;pl.mrstudios.commons&#x3C;/groupId&#x3E;
            &#x3C;artifactId&#x3E;commons-inject&#x3C;/artifactId&#x3E;
            &#x3C;version&#x3E;VERSION&#x3C;/version&#x3E;
        &#x3C;/dependency&#x3E;
    </code-block>
</tab>

<tab title="Gradle (Groovy)" group-key="gradle-groovy">
    <code-block lang="groovy">
        implementation "pl.mrstudios.commons:commons-inject:VERSION"
    </code-block>
</tab>

<tab title="Gradle (Kotlin)" group-key="gradle-kotlin">
    <code-block lang="kotlin">
        implementation("pl.mrstudios.commons:commons-inject:VERSION")
    </code-block>
</tab>

</tabs>