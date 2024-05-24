# Trap
In this document, we will explain how to add a trap during arena setup in our plugin. 

### Command
Command to add a trap is ``/deathrun setup addtrap <type> (objects)``,
where ``type`` is required trap identifier and ``objects`` is optional argument parsed individually by trap,
more explanation about how trap serializer uses ``objects`` argument is described bellow.

| Trap Type           | How trap serializer uses ``objects`` argument.                                                                            |
|---------------------|---------------------------------------------------------------------------------------------------------------------------|
| APPEARING BLOCKS    | Value from ``objects`` is used to set block type that will be appear after trap start and will disappear after trap end.  |
| DISAPPEARING BLOCKS | Value from ``objects`` is used to filter blocks from types that are not matching this argument.                           |
| PARTICLES           | Value from ``particle`` is particle that will be displayed, optionally accepting ``count`` and ``offset`` arguments.      |
| TNT                 | This trap type is not using this value, argument can be empty.                                                            |
| ARROWS              | This trap type is not using this value, argument can be empty.                                                            |

Example usages with explanation are described bellow.

| Example Usage                                            | Example Explanation                                                                          |
|----------------------------------------------------------|----------------------------------------------------------------------------------------------|
| ``/dr setup addtrap APPEARING_BLOCKS COBBLESTONE``       | All blocks in selected area will be replaced for ``COBBLESTONE``.                            |
| ``/dr setup addtrap DISAPPEARING_BLOCKS RED_TERRACOTTA`` | All blocks in selected area that is ``RED_TERRACOTTA`` will be replaced with ``AIR``.        |
| ``/dr setup addtrap PARTICLES FLAME``                    | In selected area ``FLAME`` particles will be spawned.                                        |
| ``/dr setup addtrap PARTICLES FLAME 5 0.25``             | In selected area ``FLAME`` particles will be spawned ``5 times`` with ``0.25 block`` offset. |
| ``/dr setup addtrap TNT``                                | All blocks that are ``TNT`` will be ignited when trap is active.                             |
| ``/dr setup addtrap ARROWS``                             | From ``DISPENSER`` arrows will be shot.                                                      |


<tip>
    <p>If you don't know what is <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Material.html"><b>Material</b></a> or <a href="https://jd.papermc.io/paper/1.16/org/bukkit/Particle.html"><b>Particle</b></a> check it by clicking.</p>
</tip>

### Area Selection
Using [**WorldEdit**](https://enginehub.org/worldedit) wand selects corners of a trap region.

<warning>
    <p>You must look at the button activating this trap.</p>
</warning>

### Video
<video src="https://cdn.mrstudios.pl/static/mrstudios/video/deathrun/dr_addtrap.mp4" width="1920" height="1080" preview-src="thumbnail.png" />