# GraalVM Demos

[![GraalVM Demos](https://img.shields.io/badge/GraalVM%20Demos-passing-success)](https://github.com/graalvm/graalvm-demos/actions)

This repository contains demo applications, benchmarks and examples written in Java, JavaScript, R, Ruby, and other JVM languages like Kotlin and Scala.
These programs are illustrating diverse capabilities of [GraalVM](http://graalvm.org).

## Table of Contents

### Java

| Name                      | Description                                          | Components                      | Guide/Blog Link | 
|---------------------------|------------------------------------------------------|--------------------------------|-----------------|
| [java-hello-world-maven](./java-hello-world-maven/) | This example uses a simple hello world Java application built with GraalVM Enterprise JDK and Native Image. | JDK, Native Image, Maven | TBD [GraalVM Enterprise in OCI Code Editor](https://github.com/oracle-devrel/oci-code-editor-samples/tree/main/java-samples/graalvmee-java-hello-world) [GraalVM Enterprise in OCI Cloud Shell](./java-hello-world-maven/README-Cloud-Shell.md) |
| [fortune-demo](./fortune-demo/) | Java program that simulates the traditional fortune teller Unix program. This demo shows how to run it in JIT mode, build a native executable, and finally build a mostly-static native executable. | JDK, Native Image, Maven, Gradle | - TBD - |


### Micronaut

| Name                      | Description                                          | Components                      | Guide/Blog Link | 
|---------------------------|------------------------------------------------------|--------------------------------|-----------------|
| [micronaut-hello-rest-maven](./micronaut-hello-rest-maven/) | This example uses a simple hello world REST application built with the Micronaut framework and GraalVM Enterprise JDK and Native Image. | JDK, Native Image, Micronaut, Maven | TBD [GraalVM Enterprise in OCI Code Editor](https://github.com/oracle-devrel/oci-code-editor-samples/tree/main/java-samples/graalvmee-java-micronaut-hello-rest) [GraalVM Enterprise in OCI Cloud Shell](./micronaut-hello-rest-maven/README-Cloud-Shell.md) |


### Spring Boot

| Name                      | Description                                          | Components                      | Guide/Blog Link |
|---------------------------|------------------------------------------------------|--------------------------------|-----------------|
| [spring-native-image](./spring-native-image/) | This example uses a simple Spring Boot microservice built with the Spring Boot framework and GraalVM Enterprise JDK and Native Image. | JDK, Native Image, Spring Boot, Maven | TBD [GraalVM Enterprise in OCI Code Editor](./spring-native-image/README-Code-Editor.md) [GraalVM Enterprise in OCI Cloud Shell](./spring-native-image/README-Cloud-Shell.md) |


### Scala

| Name                      | Description                                          | Components                      | Guide/Blog Link |
|---------------------------|------------------------------------------------------|--------------------------------|-----------------|
| [scalac-native](./scalac-native/) | This example demonstrates how to build a native image of the Scala compiler. | JDK, Native Image, Scala, Maven | - TBD - |


### Kotlin

| Name                      | Description                                          | Components                      | Guide/Blog Link |
|---------------------------|------------------------------------------------------|--------------------------------|-----------------|
| [java-kotlin-aot](./java-kotlin-aot/) | This example is a simple Java/Kotlin application, where a Java method accesses a Kotlin String and calls a Kotlin function, which later accesses a Java String. This example demonstrates how easy it is to interop between Java and Kotlin. | JDK, Native Image, Kotliin, Maven | - TBD - |


### Polyglot

| Name                      | Description                                          | Components                      | Guide/Blog Link | 
|---------------------------|------------------------------------------------------|--------------------------------|-----------------|
| [polyglot-chat-app](./polyglot-chat-app/) | This example uses a simple Spring Boot microservice built with the Spring Boot framework and GraalVM Enterprise JDK and Native Image. | Java, Python, R, JDK, Native Image, Spring Boot, Maven | - TBD - |
| [polyglot-debug](./polyglot-debug/) | This example uses a simple Spring Boot microservice built with the Spring Boot framework and GraalVM Enterprise JDK and Native Image. | Java, JavaScript, JDK, Native Image, Spring Boot, Maven | - TBD - |
| [polyglot-javascript-java-r](./polyglot-javascript-java-r/) | This example uses a simple Spring Boot microservice built with the Spring Boot framework and GraalVM Enterprise JDK and Native Image. | Java, JavaScript, R, JDK, Native Image, Spring Boot, Maven | - TBD - |
| [js-java-async-helidon](./js-java-async-helidon/) | This example uses a simple Spring Boot microservice built with the Spring Boot framework and GraalVM Enterprise JDK and Native Image. | Java, JavaScript, Helidon, JDK, Native Image, Maven | - TBD - |


## Running

Every top level folder here contains demo sources and the instructions on how to run that particular demo are in its README.md.
To run a demo, clone this repository, enter the demo folder, and follow steps in the README.md.

### Running in a Docker Container

Some of the demos (console-based, non-GUI) can be run inside the confinement of a Docker container.
After cloning the repository, but before running any of the demos, do the following:

1. Build the GraalVM demo Docker image of choice:
    ```
    cd docker-images
    ./buildDockerImage.sh "java11-21.2.0"
    ```

    Note: You can find valid tags to specify as parameters [here](https://github.com/graalvm/container/pkgs/container/graalvm-ce).

2. Return to the root directory of the project and run the GraalVM demo Docker container built above:
    ```
    ./runDockerImage.sh "java11-21.2.0"
    ```

Once the Docker container is running, go to the folder of the respective demo, and follow the instructions from its README.md.
Note that GraalVM runtime built with Docker will already contain additional GraalVM components such as Node.JS, Ruby, Python etc., required to run some of the demos.

Running GUI-based applications inside a Docker container requires some intermediate VNC Viewer to access the GUI interface.

1. Download and install any **VNC Viewer**. A number of free or commercial VNC Viewers can be found [here]((https://duckduckgo.com/?q=vnc+viewer+download&ia=web).
2. Wait for the container to be ready, then run VNC Viewer.
3. Log onto http://127.0.0.1:5900 (type it in, in case copy-paste does not work) via the VNC Viewer to access the GUI interface. You will get an `xterm` screen, where you can type in your commands just like the Docker console or any other CLI prompt.

Finally, from the root directory of this repository, run a Docker container with the GraalVM runtime in it:
  ```
  DEMO_TYPE="gui" ./runDockerImage.sh "java11-21.2.0"
  ```

## Tested Compatibility

The demos are normal applications and benchmarks written in Java, Kotlin, JavaScript, etc., so they are compatible with any virtual machine capable of running Java, JavaScript and so on.
You can run it on the stock JVM, Node, etc..
However, these examples were tested and are known to work with GraalVM 21.2.0 builds based on JDK 11.
Some of these demos are also [tested against the latest GraalVM release using GitHub Actions](https://github.com/graalvm/graalvm-demos/actions/workflows/main.yml).

## Further Information

* [GraalVM website](https://www.graalvm.org)
* [GraalVM on GitHub](https://github.com/oracle/graal/tree/master/compiler)
* [Scientific Publications](https://github.com/oracle/graal/blob/master/docs/Publications.md)

## License

Unless specified otherwise, all code in this repository is licensed under the [Universal Permissive License (UPL)](http://opensource.org/licenses/UPL).
Note that the submodule `fastR-examples` which is a reference to the [graalvm/examples](https://github.com/graalvm/examples) repository has a separate license.
