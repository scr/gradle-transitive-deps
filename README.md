# gradle-transitive-deps
Minimal case showing off https://github.com/gradle/gradle/issues/2005

Run `./gradlew check` to see the issue:

```
:consumer1:checkSlf4jSimple FAILED

FAILURE: Build failed with an exception.

* Where:
Build file '/Users/scr/dev/github/scr/transitive-deps/consumer1/build.gradle' line: 10

* What went wrong:
Execution failed for task ':consumer1:checkSlf4jSimple'.
> assert !runtimeClasspathFiles.grep { !it.name.startsWith('slf4j-simple') }
         ||                     |
         ||                     [/Users/scr/dev/github/scr/transitive-deps/publisher1/build/libs/publisher1-1.0-SNAPSHOT.jar, /Users/scr/.gradle/caches/modules-2/files-2.1/org.slf4j/slf4j-api/1.7.24/3f6b4bd4f8dbe8d4bea06d107a3826469b85c3e9/slf4j-api-1.7.24.jar]
         |[/Users/scr/dev/github/scr/transitive-deps/publisher1/build/libs/publisher1-1.0-SNAPSHOT.jar, /Users/scr/.gradle/caches/modules-2/files-2.1/org.slf4j/slf4j-api/1.7.24/3f6b4bd4f8dbe8d4bea06d107a3826469b85c3e9/slf4j-api-1.7.24.jar, /Users/scr/.gradle/caches/modules-2/files-2.1/org.slf4j/slf4j-simple/1.7.24/d9841ffd9d794ab26446df2c46a2ab2b8d2a183e/slf4j-simple-1.7.24.jar]
         false

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output.

BUILD FAILED

Total time: 0.882 secs

```
