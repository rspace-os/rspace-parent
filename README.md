# RSpace parent POM

Shared Maven dependency and build defaults for RSpace Java projects.

## Consumer configuration

Add JitPack (`https://jitpack.io`) to the project's Maven repositories. Select
an explicit parent release or full Git commit hash for reproducible builds.
Avoid substituting locally installed artifacts for published JitPack dependencies.

Build with Java 17 or later and Maven 3.6.3 or later. The compiler's default
Java 11 release target supports libraries, but Spring and JUnit require Java 17
to run. Applications may override the release target.

The JUnit BOM aligns Jupiter, Platform, Vintage and migration-support modules.
It does not add test engines automatically. Consumers using JUnit 4 must declare
that dependency explicitly and enable Vintage when using the JUnit Platform.
Override `junit.jupiter.version` locally when a different JUnit line is required.

Keep Mockito Core and its JUnit Jupiter integration on the same version through
`mockito.version`. Applications that need inline mocking should select the
appropriate Mockito version and mock maker locally.

The inherited logging binding targets SLF4J 1.x. Applications using SLF4J 2
must use `log4j-slf4j2-impl`. Keep logging providers consistent with the selected
SLF4J API and avoid including competing bindings.

Shared test, utility and framework defaults belong in the parent. Dependencies
and version properties used only by an application belong in that application.
Check all active consumers before removing an inherited property.

Dependency Check uses the NVD API and requires a compatible local database cache.
Configure its NVD API key through Maven settings or CI secrets; do not commit
credentials. Its managed plugin runs only when a child enables it.

## Verification

Run `mvn -B -U verify` and `mvn -B -U -Prelease package` in Boat. The parent
contains no Java tests; downstream test suites provide compatibility coverage.
