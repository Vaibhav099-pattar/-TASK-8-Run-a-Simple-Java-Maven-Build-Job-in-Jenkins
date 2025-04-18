# -TASK-8-Run-a-Simple-Java-Maven-Build-Job-in-Jenkins
Requirements
Jenkins (jenkins/jenkins:lts via Docker)
Java JDK 8 or 11
Maven ( 3.8.6)
 Process
 STEP.1. Create a simple Java app
 2. src/main/java/HelloWorld.java
 3. .java
 4. public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Jenkins + Maven!");
    }
}

STEP.2. Create a pom.xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 
         http://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>hello</artifactId>
    <version>1.0</version>

    <build>
        <plugins>
            <plugin>
                <groupId>org.apache.maven.plugins</groupId>
                <artifactId>maven-compiler-plugin</artifactId>
                <version>3.8.1</version>
                <configuration>
                    <source>1.8</source>
                    <target>1.8</target>
                </configuration>
            </plugin>
        </plugins>
    </build>
</project>
STEP 3.Start Jenkins via Docker->docker run -p 8081:8080 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts
STEP 4.Visit http://localhost:8081
STEP 5. Create a Jenkins Freestyle Project
        a.Go to Jenkins Dashboard → New Item
        b.Enter name: hello-java-maven
        c.Choose Freestyle project
        d.In Build section->Click Add build step → Invoke top-level Maven targets
          Goals: clean package
STEP:6 Build & Verify
  a.Click Save
  b.Click Build Now
  c.Click on the build → Console Output
  

          
        
      
        


