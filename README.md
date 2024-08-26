# Purpose
This is overridden version of [opentracing-contrib/java-rabbitmq-client](https://github.com/opentracing-contrib/java-rabbitmq-client) that fixes library problems.
Library is deprecated and not maintained anymore.
It should replaced with OpenTelemetry.

In the meantime, all fixes for SmartRecruiters will reside here.

# Publishing changes
1. Adjust version in `pom.xml`
2. Replace `{SR Nexus URL}` in `pom.xml` with URL to nexus
3. Create settings for maven in `~/.m2/settings.xml
```xml
<settings xmlns="http://maven.apache.org/SETTINGS/1.0.0"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://maven.apache.org/SETTINGS/1.0.0
    https://maven.apache.org/xsd/settings-1.0.0.xsd">
    <localRepository/>
    <interactiveMode/>
    <usePluginRegistry/>
    <offline/>
    <pluginGroups/>
    <servers>
        <server>
            <id>sr-nexus</id>
            <username>*********************************************</username>
            <password>*******************************</password>
        </server>
    </servers>
    <mirrors/>
    <proxies/>
    <profiles/>
    <activeProfiles/>
</settings>
```
4. Run `mvn clean install`
5. Run `mvn source:jar deploy`