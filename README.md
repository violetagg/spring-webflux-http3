# Example for configuring HTTP/3 in Spring Boot application

## Prerequisites

### Configure Reactor Netty version

Bump `Reactor BOM` version in `pom.xml`
```xml
<properties>
	<reactor-bom.version>2024.0.0</reactor-bom.version>
</properties>
```

### Add dependency to Netty Http3 Codec

In `pom.xml` add dependency to [netty-incubator-codec-http3](https://github.com/netty/netty-incubator-codec-http3)
```xml
<dependency>
	<groupId>io.netty.incubator</groupId>
	<artifactId>netty-incubator-codec-http3</artifactId>
	<version>0.0.28.Final</version>
	<scope>runtime</scope>
</dependency>
```
### Configure SSL Bundle

In `application.properties` add the `SSL` configuration
```properties
spring.ssl.bundle.jks.server-http3.key.alias...
spring.ssl.bundle.jks.server-http3.keystore...
```
More information about [SSL Bundle](https://docs.spring.io/spring-boot/reference/features/ssl.html) settings:

## Available endpoints

### Hello Endpoint
This endpoint showcases `HTTP/3` server support

```shell
curl --http3 https://localhost:8443/hello -v
```

### Remote Endpoint
This endpoint showcases `HTTP/3` client support

```shell
curl --http3 https://localhost:8443/remote -v 
```