# Submarine
funny gradle project displaying an issue I have

this is about an issue discussed [here](http://forums.gradle.org/gradle/topics/dependency-substitution-wrong-with-more-than-one-sub-project-with-same-name) and [here](http://stackoverflow.com/questions/28458511/gradle-confusion-dependency-with-duplicate-sub-project-names)

This issue I have is: 

```
    :sub-1:sub-a:other:compileJava
    /home/fwelland/NetBeansProjects/Submarine/sub-1/sub-a/other/src/main/java/com/fhw/tools/Poser.java:4: error: package com.fhw.util does not exist
    import com.fhw.util.*; 
    ^
    1 error
    :sub-1:sub-a:other:compileJava FAILED

    FAILURE: Build failed with an exception.
```

and this: 

```
    [fwelland@wellandf3 other]$ gradle dependencies 
    :sub-1:sub-a:other:dependencies

    ------------------------------------------------------------
    Project :sub-1:sub-a:other
    ------------------------------------------------------------

    archives - Configuration for archive artifacts.
    No dependencies

    compile - Compile classpath for source set 'main'.
    +--- project :sub-1:common
    \--- project :sub-1:sub-a:common -> project :sub-1:common

    default - Configuration for default artifacts.
    +--- project :sub-1:common
    \--- project :sub-1:sub-a:common -> project :sub-1:common

    runtime - Runtime classpath for source set 'main'.
    +--- project :sub-1:common
    \--- project :sub-1:sub-a:common -> project :sub-1:common

    testCompile - Compile classpath for source set 'test'.
    +--- project :sub-1:common
    \--- project :sub-1:sub-a:common -> project :sub-1:common

    testRuntime - Runtime classpath for source set 'test'.
    +--- project :sub-1:common
    \--- project :sub-1:sub-a:common -> project :sub-1:common

    (*) - dependencies omitted (listed previously)

    BUILD SUCCESSFUL

    Total time: 2.973 secs
```
