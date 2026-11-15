## 3.3.0-SNAPSHOT (unreleased)
 * Publish a JitPack snapshot for coordinated downstream CI; this is not the final 3.3.0 release.
 * Update build plugins: Surefire 3.6.1, Source 3.4.0, Javadoc 3.12.0, Enforcer 3.7.0, Toolchains 3.3.0, Compiler 3.16.0, Dependency Check 13.0.0.
 * Update AssertJ 3.27.7, Mockito 3.12.4, Lombok 1.18.48, SLF4J 1.7.36, Vavr 0.10.7, Commons Codec 1.23.0 and Commons Lang 3.22.0.
 * Update Jackson BOM 2.23.0, Log4j BOM/API/Core/binding 2.26.1, Spring Security Crypto 6.5.11, JAXB API 4.0.5, jsoup 1.24.1 and Hibernate Validator property 8.0.6.Final.
 * Import the JUnit BOM using junit.jupiter.version (default 6.1.3), aligning Platform and optional Vintage modules; legacy consumers can select JUnit 5 locally without source migration.
 * Move web-only Hibernate ORM/Search, iCal4j, ImageJ, Shiro and Thumbnailator properties into rspace-web; remove the unused Jakarta Mail API property.
 * Retain Hamcrest 1.3, Servlet 6.1.0, Hibernate Validator and Jakarta Validation properties because other active consumers use them. Web continues to select Servlet 6.0 and Hamcrest 3.0 locally.
 * Keep major migrations (Spring 7, Jackson 3, Hibernate 7, HttpClient 5, Vavr 1 and Mockito 5) outside the shared parent baseline.

## 3.2.1 2026-11-03
 * Jackson 2.22.2 -> 2.22.4
 * Log4j 2.23.1 -> 2.25.5
 * log4j-bom imported in dependencyManagement so downstream builds converge all Log4j artifacts on log4j.version

## 3.2.0 2026-08-31
 * JUnit 4 -> 6

## 3.1.0 2026-08-20
 * Shiro 2.1.0 -> 3.0.0

## 3.0.1 2026-08-03
 * spring version 6.2.15 -> 6.2.19
 * spring-framework-bom imported in dependencyManagement so downstream builds converge all Spring artifacts on spring.version

## 3.0.0 2026-04-29
 * Spring 6 / Hibernate 6 / Jakarta EE migration (RSDEV-444)
 * spring-security-crypto -> 6.5.9
 * Hibernate -> 6.4.4 with Hibernate Search 7
 * Shiro 2.1.0 (Jakarta-compatible)
 * jakarta.xml.bind-api replaces javax.xml.bind:jaxb-api
 * commons-text 1.14.0 added
 * **BREAKING** version properties renamed for Jakarta: javax-mail-api.version -> jakarta.mail-api.version, javax.validation.version -> jakarta.validation.version (downstream builds referencing the old names must update)

## 2.2.0 (11th June, 2026)
 * Remove ical4j (reverted in 2.2.1)

## 2.1.4
 * commons-logging 1.2 -> 1.3.5 
 * commons-validator 1.7 -> 1.9.0
 * commons-digester 2.1

## 2.1.2, 2.1.3
  * commons-codec 1.11 -> 1.13
  * commons-io 2.14.0 -> 2.20.0

## 2.1.1 
  * spring version 5.3.25 -> 5.3.39 (minor update)

## 2.1.0 - update various dependencies:
  * commons-lang:2.6 is now replaced with commons-lang3:3.18 **NOTE** this requires changing import statements in java classes relying on commons-lang
  * commons-io 2.13.0 -> 2.14.0
  * commons-beanutils 1.9.4 -> 1.11.0 
  * commons-collections 4.4 -> 4.5.0
  * spring-security-crypto 4.2.11.RELEASE -> 6.4.5

## 2.0.2 
  * update Apache Shiro dependency version (1.9.0 -> 1.13.0)

## 2.0.1 
  * remove maven-toolchains-plugin from plugins list, to allow building with jitpack

## 2.0.0
   * use log4j2; also initial version for open-source
