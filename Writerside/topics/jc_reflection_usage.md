# Usage
In this document, you will find how to use `commons-reflection` in your project.

### Example
```Java
package com.example;

import pl.mrstudios.commons.reflection.Reflections;

public class Example {

    public static void main(String[] args) {
        
        /* Filter by Annotation */
        new Reflections<IPortal>("com.example")
                .getClassesAnnotatedWith(Portal.class)
                .forEach((portal) -> {
                    try {
                        portal.getDeclaredConstructor().newInstance();
                    } catch (Exception exception) {
                        exception.printStackTrace();
                    }
                });
        
        /* Filter by Interface */
        new Reflections<IPortal>("com.example")
                .getClassesImplementing(IPortal.class)
                .forEach((portal) -> {
                    try {
                        portal.getDeclaredConstructor().newInstance();
                    } catch (Exception exception) {
                        exception.printStackTrace();
                    }
                });
        
    }
    
    public static @interface Portal {}
    public static interface IPortal {}
    
}
```