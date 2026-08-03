## 3.0.1 2026-08-03
 * spring version 6.2.15 -> 6.2.19 (minor update, includes fixes for ten CVEs)

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
