Salesforce Marketing Cloud Java SDK
===================================

The Salesforce Marketing Cloud Java SDK enables developers to easily
access the Salesforce Marketing Cloud (formerly ExactTarget) via the
Java platform. Among other things, the SDK:

* automatically acquires and refreshes Marketing Cloud
  access tokens

* enables developers to access both Marketing Cloud SOAP
  and REST APIs in the same session

* exposes simplified versions of the most commonly used Marketing
  Cloud objects and methods as Java native objects

* provides passthroughs so developers can access the full
  REST and SOAP APIs directly when they need to go beyond
  the simplified interfaces

* adds "sugar" methods for the most commonly used Marketing
  Cloud features that make it easy to use those features (e.g.,
  the SDK provides a SQL-like interface to data extensions)

For more information about the Java SDK and how to use it, please see
the Javadocs at http://salesforce-marketingcloud.github.io/FuelSDK-Java/.

New Features in Version 1.3.2 
------------
* Added support for your tenant’s endpoints - [More Details](https://developer.salesforce.com/docs/atlas.en-us.mc-apis.meta/mc-apis/your-subdomain-tenant-specific-endpoints.htm)
* REST, Auth endpoints are configurable. If not specified in the fuelsdk.properties file,
they are defaulted to "https://www.exacttargetapis.com" for REST and 
"https://auth.exacttargetapis.com" for Auth.
* SOAP endpoint is also configurable. If not specified in the fuelsdk.properties file, 
it is defaulted to "https://webservice.exacttarget.com/service.asmx"
* Removed the legacyToken query string parameter support.


Installation
------------

The easiest way to install the Java SDK is via Maven&mdash;simply add the following dependency to your project's `pom.xml`:

    <dependency>
      <groupId>com.github.salesforce-marketingcloud</groupId>
      <artifactId>fuelsdk</artifactId>
      <version>1.3.2</version>
    </dependency>

Maven will automatically resolve, download, and install all dependencies for you.

You can also download a jar file from the [Releases](https://github.com/salesforce-marketingcloud/FuelSDK-Java/releases) page or clone the repository and build a jar file yourself in the standard way. If you go this route, you'll need to ensure you have manually downloaded and installed all dependencies ([Apache CXF](http://cxf.apache.org), [Apache Commons BeanUtils](http://commons.apache.org/proper/commons-beanutils), [Apache log4j 1.x](http://logging.apache.org/log4j/1.2/), and [Google Gson](https://code.google.com/p/google-gson)) to your class path.

Once you have the SDK installed, you'll need to obtain a client ID and client secret from App Center and place them in `fuelsdk.properties` using `src/main/resources/fuelsdk.properties.template` as a starting template. Theses values authenticate you to the Saleforce Marketing Cloud API.
