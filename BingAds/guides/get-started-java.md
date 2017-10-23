---
title: "Get Started Using Java with Bing Ads Services"
ms.service: "bing-ads"
ms.topic: "article"
ms.date: 11/1/2017
author: "eric-urban"
ms.author: "eur"
description: Install the Bing Ads Java SDK and discover code examples.
---
# Get Started Using Java with Bing Ads Services
To get started developing Bing Ads applications with Java, you can start with the [provided examples](~/guides/code-examples.md) or follow one of the application walkthroughs for a [Web](~/guides/walkthrough-web-application-java.md) or [Desktop](~/guides/walkthrough-desktop-application-java.md) application. The examples have been developed with the Bing Ads Java [SDK](~/guides/client-libraries.md) and run with the Eclipse Java EE IDE for Web Developers, Luna Service Release 1 (4.4.1). For Eclipse downloads, see [http://www.eclipse.org/downloads/](http://www.eclipse.org/downloads/). Your custom configuration may vary.

You will need user credentials with access to Bing Ads either in [production](https://secure.bingads.microsoft.com/) or [sandbox](https://secure.sandbox.bingads.microsoft.com/Auth?EnvContext=Sandbox). For the production environment you will need a [production developer token](~/guides/get-started.md#get-developer-token). All sandbox clients can use the universal sandbox developer token i.e., **BBD37VB98**. For more information, please see [Get Started With the Bing Ads API](../guides/get-started.md) and [Sandbox](../guides/sandbox.md).

To authenticate with a [Microsoft Account](https://account.microsoft.com/account) (email address username) in production, you must also must [register](../guides/authentication-oauth.md#registerapplication) an application and get the corresponding client identifier. You also need to take note of the client secret and redirect URI if you are developing a web application. For authentication details, see [Authentication With the SDKs](~/guides/sdk-authentication.md#oauth).

## <a name="installation"></a>Install the SDK
The Bing Ads Java [SDK](~/guides/client-libraries.md) depends on the libraries listed at the [Maven Repository](http://mvnrepository.com/artifact/com.microsoft.bingads/microsoft.bingads/).

When you create a Maven project and include the *microsoft.bingads* Maven artifact as shown below, additional dependencies are installed automatically. If you are not using a Maven project, you must include the correct version of each dependency. For more information, please see the [Walkthrough: Bing Ads Web Application in Java](../guides/walkthrough-web-application-java.md) or [Walkthrough: Bing Ads Desktop Application in Java](../guides/walkthrough-desktop-application-java.md) application examples.

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
  ...
  <dependencies>
    <dependency>
      <groupId>com.microsoft.bingads</groupId>
      <artifactId>microsoft.bingads</artifactId>
      <version>11.5.5</version>
    </dependency>
  </dependencies>
</project>
```
> [!NOTE]
> Version 11.5.5 is included as an example. For details about the latest SDK dependency version, please see the [Bing Ads Java SDK GitHub README.md](https://github.com/BingAds/BingAds-Java-SDK).

## <a name="walkthrough"></a>Walkthroughs
Once you have the Bing Ads Java [SDK](~/guides/client-libraries.md) installed, you can either browse the [Bing Ads Code Examples](../guides/code-examples.md), download the examples from [GitHub](https://github.com/BingAds/BingAds-Java-SDK/tree/master/examples), or follow one of the application walkthroughs for a [Web](../guides/walkthrough-web-application-java.md) or [Desktop](../guides/walkthrough-desktop-application-java.md) application.

## See Also
[Bing Ads Client Libraries](../guides/client-libraries.md)    
[Bing Ads Code Examples](../guides/code-examples.md)    
[Bing Ads Web Service Addresses](../guides/web-service-addresses.md)  
[Handling Service Errors and Exceptions](~/guides/handle-service-errors-exceptions.md)  
[Sandbox](../guides/sandbox.md)  