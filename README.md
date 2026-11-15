# RSpace parent POM

Shared Maven dependency and build defaults for RSpace Java projects.

## Testing 3.3.0 before release

The `3.3.0` branch declares `3.3.0-SNAPSHOT`. JitPack exposes a branch snapshot
as `com.github.rspace-os:rspace-parent:3.3.0-SNAPSHOT`. Downstream CI PRs should
pin the full parent commit hash instead so a rebuild tests the same candidate.
Resolve that commit from JitPack before starting downstream builds. Do not use
`mvn install` to substitute a locally built parent for the published artifact.

The final `3.3.0` release and downstream release pins follow successful CI;
the snapshot does not publish a final release tag.

## Consumer compatibility

Build with Java 17 or later and Maven 3.6.3 or later. The compiler's default
Java 11 release target is retained for libraries, but the Spring 6 and JUnit 6
baseline requires Java 17 to run. Applications may override the release target.

JUnit defaults to 6.1.3. Consumers still using JUnit 5 migration support must
define `junit.jupiter.version` locally to select a JUnit 5 BOM and declare any
JUnit 4 dependency explicitly (4.13.2). The BOM aligns Jupiter, Platform and
Vintage; it does not add a test engine automatically.

Mockito remains on 3.12.4 to avoid forcing the Mockito 5 inline mock maker on
every library. Consumers may override `mockito.version`, keeping Core and
JUnit Jupiter integration on the same version.

SLF4J remains on 1.7.36 with `log4j-slf4j-impl`. Applications using SLF4J 2
must replace that inherited binding with `log4j-slf4j2-impl`.

These properties now belong to `rspace-web`: `hibernate.version`,
`hibernate-search.version`, `ical4j.version`, `imagej.version`, `shiro.version`
and `thumbnailator.version`. `jakarta.mail-api.version` was unused and removed.
Shared Hamcrest, Servlet, Hibernate Validator and Jakarta Validation properties
remain here because other active consumers reference them.

Dependency Check 13 uses the NVD API and requires a compatible local database
cache. Configure its NVD API key through Maven settings or CI secrets; do not
commit credentials. Its managed plugin is only executed when a child enables it.

## Verification

Run `mvn -B -U verify` and `mvn -B -U -Prelease package` in Boat. The parent
contains no Java tests; downstream test suites provide compatibility coverage.
