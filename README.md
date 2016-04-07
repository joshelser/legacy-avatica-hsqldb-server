## HSQLDB Avatica server for older Apache Calcite releases

Apache Calcite Avatica 1.8.0 will include a standalone artifact
which starts an Avatica server instance using an embedded
HSQLDB server. This project aims to provide the same functionality
against older versions of Avatica/Calcite.

This is desired to enable cross-version compatibility tests for
Avatica's RPC framework.

### Building

By default, Calcite 1.6.0 is built against. This can be changed
by specifying `-Dcalcite.version=<...>` on the Maven command line.

To build against Calcite-1.7.x series releases, the `post-avatica-split`
Maven profile must also be activated, e.g. `-Dcalcite.version=1.7.1 -Ppost-avatica-split`.

### Running

The server can be started using the provided shaded jar

  `java -jar target/legacy-avatica-hsqldb-server-0.0.1-SNAPSHOT-avatica-1.6.0.jar`
