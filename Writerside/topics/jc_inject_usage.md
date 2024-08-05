# Usage
In this document, you will find how to use `commons-inject` in your project.

### Example
```Java
package com.example;

import pl.mrstudios.commons.inject.Injector;
import pl.mrstudios.commons.inject.annotation.Inject;

public class Example {

    public static void main(String[] args) {

        Injector injector = new Injector()
                .registerService(args)
                .registerService(Enemy.class, new Enemy("An Enemy"));

        injector.inject(AnClass.class);

    }

    public static class AnClass {

        @Inject
        public AnClass(Enemy enemy, String[] args) {
            System.out.println(String.join(" ", args));
        }

    }
    
    public static record Enemy(String name) {}

}
```
<tip>
    <p>Parameters in the constructor may be in random position, you don't need to set parameters in constructor ordered by registry.</p>
</tip>