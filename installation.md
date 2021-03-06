# Installation
## Prerequisites
1. [Install JDK and set JAVA_HOME as an Environment variable](/setup/jdk.md)
1. [Download Android SDK and set ANDROID_HOME as an Environment variable](/setup/android_sdk.md)
1. [Install Maven and setup the Maven Android SDK Deployer](/setup/maven_android_sdk_deployer.md)

## ATMOSPHERE
1. Clone the following repositories from the Musala GitHub account:
  * ```atmosphere-commons```
  * ```atmosphere-agent-device-lib```
  * ```atmosphere-server-agent-lib```
  * ```atmosphere-client-server-lib```
  * ```atmosphere-bitmap-comparison```
  * ```atmosphere-ime```
  * ```atmosphere-service```
  * ```atmosphere-uiautomator-bridge```
  * ```atmosphere-client```
  * ```atmosphere-agent```
  * ```atmosphere-server```

1. Following the order of the above list, run:  
```gradlew build``` (on Windows) or ```./gradlew build``` (on Linux/macOS),  
and if the build is successful:  
```gradlew publishToMavenLocal``` (on Windows) or ```./gradlew publishToMavenLocal``` (on Linux/macOS)  
in the root directory of each of the downloaded repositories.

1. Run the Server by executing:  
```gradlew run``` (on Windows) or ```./gradlew run``` (on Linux/macOS)   
in the ```atmosphere-server``` root directory and wait until you see an output similar to this:  
```>> com.musala.atmosphere.server.state.RunningServer$InnerRunThread.run(RunningServer.java:47) 24 Aug 2016 11:08:49 - Running Server...```  
Leave the terminal open.

1. Connect a physical device or run an Android emulator.

1. Run the Agent by executing:  
```gradlew run``` (on Windows) or ```./gradlew run``` (on Linux/macOS)   
in the ```atmosphere-agent``` root directory and wait until you see an output similar to this:  
```com.musala.atmosphere.agent.AgentManager.createWrapperForDevice(AgentManager.java:378) 24 Aug 2016 12:53:43 - Created wrapper for device with bindingId = 0149BCA70C01D00F```  

1. Connect the Agent to the Server by running ```connect <port>``` in the Agent terminal. By default the Server port is set to ```1980```. It could be changed by editing the ```pool.manager.rmi.port``` property in the ```server.properties``` file in the ```atmosphere-server``` root directory.

You should now be set to [run Atmosphere tests](https://github.com/MusalaSoft/atmosphere-docs/tree/documentation-readme#atmosphere-tests).
