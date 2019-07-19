## Building Spring Boot application with Gradle plus Groovy

1-Make a **Gradle** Project by default language syntax with IDE

2- Make Project package structure(**ir.seefa.sample.project**) in _src/main/java_ and _src/test/java_

* Hint: Be careful about word spelling for packages because Test classes will not able to run SpringBoot Test Runner if *Packages* or *Classes* are not match names.

3- add below codes to **build.gradle** or **build.gradle.kts** to get **Spring Boot** dependencies and project features(Project name, Project version, Java plugin, dependencies, Add a task to making JAR file, Java configuration, so on)

```
 plugins {
     id 'org.springframework.boot' version '2.1.6.RELEASE'
     id 'java'
 }
 
 apply plugin: 'io.spring.dependency-management'
 
 group = 'ir.seefa.sample.project'
 version = '1.0-SNAPSHOT'
 sourceCompatibility = '11'
 
 
 repositories {
     mavenCentral()
 }
 
 dependencies {
     implementation group: 'org.springframework.boot', name: 'spring-boot-starter-web'
     testImplementation group: 'org.springframework.boot', name: 'spring-boot-starter-test'
 }
 ```
 
* Tips: 
    1) plugins -> _java_, _org.springframework.boot_
    2) apply plugin -> _io.spring.dependency-management_
    3) Project properties: _Group_,_Version_,_SourceCompatibility_
    4) repositories
    5) dependencies implementation -> _spring-boot-starter-web_, testImplementation -> spring-boot-starter-test'

4- Add **SpringBootStarterApplication** class to has been made package from Step 2 with following code:

```
package ir.seefa.sample.project;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class SpringBootStarterApplication {

	public static void main(String[] args) {
		SpringApplication.run(SpringBootStarterApplication.class, args);
	}

}
```

5- Add **application.properties** file to _src/main/resources_ path for apply application configuration before run such server port as follows:

```
server.port=9090
```

6- Add **SpringBootStarterApplicationTests** class to _/src/test/java/[Package_Name]_

6- run command **gradle** in command line

7- run command **gradle tasks** in command line

8- Build your project with Gradle Wrapper => Run in command line(gradle wrapper --gradle-version 5.4.1)

9- After passing step No.8, we can only run this command to build project(**./gradlew build**)

10- Run this command will execute our Application(**./gradlew run**)  or Run **SpringBootStarterApplication** directly.
