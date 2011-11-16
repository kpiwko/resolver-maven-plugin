ShrinkWrap Resolver Maven plugin
================================

The plugin allows ShrinkWrap Maven Resolver (SWR) to enrich the test execution with properties retrieved for parent Maven process.
This means you no longer have to specify `settings.xml`, `pom.xml` etc. directly in your tests but ShrinkWrap Maven Resolver can retrieve them them.

This does not work in the IDE (so far).

Note, there is no version of SWR which is able to use these. Meanwhile, you can retrieve settings by your own from following System Properties:

* `maven.execution.pom-file`
* `maven.execution.user-settings`
* `maven.execution.global-settings`
* `maven.execution.offline`
* `maven.execution.active-profiles`

Requirements
------------

* Maven 3.0.3 or upper
* Maven Surefire Plugin 2.9 or upper
* Java 5 or upper

Usage
-----

To enable the plugin add following in your project:

    <plugin>
        <groupId>org.jboss.shrinkwrap.resolver</groupId>
        <artifactId>resolver-maven-plugin</artifactId>
        <version>1.0.0-alpha-1-SNAPSHOT</version>
        <executions>
            <execution>
                <goals>
                    <goal>propagate-execution-context</goal>
                </goals>
            </execution>
       </executions>
    </plugin>

This will allow you to get the enriched environment when executing tests with ShrinkWrap Maven Resolver from command line.

Usage in the IDE
----------------

Coming soon. Meanwhile, set the properties by your own for JUnit/TestNG runners.

