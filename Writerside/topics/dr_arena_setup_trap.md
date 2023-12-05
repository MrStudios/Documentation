# Trap
In this document, we will explain how to add a trap during arena setup in our plugin. 

### Command
Command to add a trap is ``/deathrun setup addtrap <type> (material)``, where ``type`` is required trap identifier and ``material`` is optional argument that must be [**Material**](https://jd.papermc.io/paper/1.16/org/bukkit/Material.html) enum value. Argument ``material`` is used differently by every trap type, bellow you can find table how this argument is used by official traps.

| Trap Type           | How trap serializer uses this argument.                                                                                   |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| APPEARING BLOCKS    | Value from ``material`` is used to set block type that will be appear after trap start and will disappear after trap end. |
| DISAPPEARING BLOCKS | Value from ``material`` is used to filter blocks from types that are not matching this argument.                          |
| TNT                 | This trap type is not using this value, argument can be empty.                                                            |

### Area Selection
Using [**WorldEdit**](https://enginehub.org/worldedit) wand selects corners of a trap region.

<warning>
    <p>You must look at the button activating this trap.</p>
</warning>

### Video
<video src="https://cdn.mrstudios.pl/static/mrstudios/video/deathrun/dr_addtrap.mp4" width="1920" height="1080" preview-src="thumbnail.png" />