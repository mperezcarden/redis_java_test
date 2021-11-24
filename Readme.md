# Redis Java Test

Based on these quickstarts: 
*[Samples repository for Azure Cache for Redis](https://github.com/Azure-Samples/azure-cache-redis-samples/tree/main/quickstart/java)
* [Quickstart: Use Azure Cache for Redis in Java](https://docs.microsoft.com/en-us/azure/azure-cache-for-redis/cache-java-get-started)

# Pre requisites

1. Azure Subscription
2. Azure Cache for Redis
3. Apache Maven

# Instaing Apache Maven

## 1. Check JDK

That's on Windows > Advanced system setttings > Environment variables ``JAVA_HOME``. Mine was at ``C:\Users\<username>\AppData\Local\Programs\AdoptOpenJDK\jdk-11.0.10.9-hotspot\``

I have to re-install JDK
New was at: C:\Program Files\Java\jdk-17.0.1\

Do not forget to update the "JAVA_HOME" and the System "PATH" as described here: https://mkyong.com/java/how-to-set-java_home-on-windows-10/

Test JDK version

```
java -version
```

## 2. Download Apache Maven

Official site: https://maven.apache.org/download.cgi

You can also use this information to install Apache Maven system variables: https://mkyong.com/maven/how-to-install-maven-in-windows/

Test after install

```
mvn --version
```

# Set up the working environment

Command prompt or terminal

PowerShell
```
set REDISCACHEHOSTNAME=<YOUR_HOST_NAME>.redis.cache.windows.net
set REDISCACHEKEY=<YOUR_PRIMARY_ACCESS_KEY>
```

```
export REDISCACHEHOSTNAME=<YOUR_HOST_NAME>.redis.cache.windows.net
export REDISCACHEKEY=<YOUR_PRIMARY_ACCESS_KEY>
```

# Run the Sample code

Sample code usually includes a Project Object Model ``pom.xml`` file.

```
mvn compile
mvn exec:java -D exec.mainClass=example.demo.App
```

# TODO: Error message

```
[ERROR] Failed to execute goal org.codehaus.mojo:exec-maven-plugin:3.0.0:java (default-cli) on project redistest: An exception occured while executing the Java class. hostname can't be null ->
 [Help 1]
org.apache.maven.lifecycle.LifecycleExecutionException: Failed to execute goal org.codehaus.mojo:exec-maven-plugin:3.0.0:java (default-cli) on project redistest: An exception occured while executing the Java class. hostname can't be null
```

```
Caused by: java.lang.IllegalArgumentException: hostname can't be null
```

Try this to check the error message again

```
mvn -e -f pom.xml compile exec:java -D exec.mainClass=example.demo.App
```