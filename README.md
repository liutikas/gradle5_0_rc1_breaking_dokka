This project demostrates breakage of Dokka when upgrading to Gradle 5.0-rc1

`./gradlew tasks` will fail with:
```
e: /ssd/ssd1/temp/HopefullyThisBreaks/buildSrc/src/main/kotlin/test/Test.kt: (1, 35): Unresolved reference: DokkaPlugin
> Task :buildSrc:compileKotlin FAILED
```

However, if you move back to Gradle 4.10.1 by changing it in `gradle/wrapper/gradle-wrapper.properties` the command above works fine.

Something in the classpath added by Gradle seems to break Dokka usage in `buildSrc`