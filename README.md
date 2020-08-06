ksuid - Java Version
A Java implementation of the Segment's KSUID library. For a full treatment of why this came about, you can read the blog post on their website.

Maven Central
This library can be downloaded from Maven Central by adding the following as a dependency in your pom.xml file:

``` xml
<dependency>
    <groupId>com.ruishanio</groupId>
    <artifactId>ksuid</artifactId>
    <version>1.1.0</version>
</dependency>
```

Quick Start
``` java
final Ksuid ksuid = new Ksuid();
final String uid = ksuid.generate();
// e.g. output: Be785NYYxP29BJiAJPupfsXuGpR

final String decoded = ksuid.print(uid);
// e.g. output: Time: 2017-07-08T21:13:08Z[UTC]
//              Timestamp: 1499548388
//              Payload: [-42, 24, -60, -3, -66, 38, 32, 9, 62, -22, 95, -79, 123, -122, -91, 0]

final KsuidComponents components = ksuid.parse(uid);
// components.getTimestamp();
// components.getPayload();
```

# History
- 2.0.0: Breaking change. This release candidate version will generate KSUIDs cross-compatible with Go and Node.js implementations. The Base62 library has been removed in favor of a different implementation.
- 1.0.1: Initial public release.
