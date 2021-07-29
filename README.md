[![Maven Central](https://img.shields.io/maven-central/v/io.github.fslev/maven-cucumber-reporting-extended.svg?label=Maven%20Central)](https://search.maven.org/search?q=g:%22io.github.fslev%22%20AND%20a:%22maven-cucumber-reporting-extended%22)

This a prettified version of maven-cucumber-reporting  

Maven mojo for the cucumber-reporting - put this into your `pom.xml` and run `mvn verify` so cucumber reports will be generated in `target/cucumber-html-reports`  

Read more about the project and configuration here:
- [cucumber-reports](https://github.com/damianszczepanik/cucumber-reporting)  
- [maven-cucumber-reports](https://github.com/damianszczepanik/maven-cucumber-reporting)

## Set maven plugin inside you Maven project
```
<build>
    <plugins>
        <plugin>
            <groupId>io.github.fslev</groupId>
            <artifactId>maven-cucumber-reporting-extended</artifactId>
            <version>(see latest version above)</version>
            <executions>
                <execution>
                    <id>execution</id>
                    <phase>verify</phase>
                    <goals>
                        <goal>generate</goal>
                    </goals>
                    <configuration>
                        <projectName>My project</projectName>
                        <skip>false</skip>
                        <outputDirectory>${project.build.directory}</outputDirectory>
                        <inputDirectory>${project.build.directory}/cucumber-report</inputDirectory>
                        <jsonFiles>
                            <param>**/*.json</param>
                        </jsonFiles>
                        <classificationFiles>
                            <classificationFile>cucumber-report/classification.properties
                            </classificationFile>
                        </classificationFiles>
                        <checkBuildResult>false</checkBuildResult>
                    </configuration>
                </execution>
            </executions>
        </plugin>
    </plugins>
</build>
```