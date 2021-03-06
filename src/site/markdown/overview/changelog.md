# Changelog

## ????? - 5.5.0-SNAPSHOT

**New Supported Languages:**

*   CPD now supports Perl. See [PR#82](https://github.com/pmd/pmd/pull/82).

**Feature Request and Improvements:**

*   CPD: New command line parameter `--ignore-usings`: Ignore using directives in C# when comparing text.
*   A JSON-renderer for PMD which is compatible with CodeClimate. See [PR#83](https://github.com/pmd/pmd/pull/83).

**New/Modified/Deprecated Rules:**

*   Java
    *   Logging Java: **InvalidSlf4jMessageFormat** (rulesets/java/logging-java.xml/InvalidSlf4jMessageFormat)<br/>
        Check for invalid message format in slf4j loggers.
*   java-comments/CommentRequired: New property `serialVersionUIDCommentRequired` which controls the comment requirements
    for *serialVersionUID* fields. By default, no comment is required for this field.
*   java-design/UseVargs: public static void main method is ignored now and so are methods, that are annotated
    with Override. See [PR#79](https://github.com/pmd/pmd/pull/79).

**Pull Requests:**

*   [#25](https://github.com/adangel/pmd/pull/25): Added option to exclude C# using directives from CPD analysis
*   [#27](https://github.com/adangel/pmd/pull/27): Added support for Raw String Literals (C++11).
*   [#29)(https://github.com/adangel/pmd/pull/29): Added support for files with UTF-8 BOM to JSP tokenizer.
*   [#30](https://github.com/adangel/pmd/pull/30): Removed file filter for files that are explicitly specified on the CPD command line using the '--files' command line option.
*   [#31](https://github.com/adangel/pmd/pull/31): Added file encoding detection to CPD.
*   [#32](https://github.com/adangel/pmd/pull/32): Extended Objective-C grammar to accept UTF-8 escapes (\uXXXX) in string literals.
*   [#72](https://github.com/pmd/pmd/pull/72): Added capability in Java and JSP parser for tracking tokens.
*   [#73](https://github.com/pmd/pmd/pull/73): Add rule to look for invalid message format in slf4j loggers
*   [#74](https://github.com/pmd/pmd/pull/74): Fix rendering CommentDefaultAccessModifier description as code
*   [#75](https://github.com/pmd/pmd/pull/75): RuleSetFactory Performance Enhancement
*   [#76](https://github.com/pmd/pmd/pull/76): fix formatting typos in an example of the DoNotCallGarbageCollectionExplicitly rule
*   [#77](https://github.com/pmd/pmd/pull/77): Fix various typos
*   [#78](https://github.com/pmd/pmd/pull/78): Add Builder pattern check to the MissingStaticMethodInNonInstantiatableClass rule
*   [#79](https://github.com/pmd/pmd/pull/79): do not flag public static void main(String[]) as UseVarargs; ignore @Override for UseVarargs
*   [#80](https://github.com/pmd/pmd/pull/80): Update mvn-plugin.md
*   [#82](https://github.com/pmd/pmd/pull/82): Add Perl support to CPD.
*   [#83](https://github.com/pmd/pmd/pull/83): Adds new Code Climate-compliant JSON renderer
*   [#84](https://github.com/pmd/pmd/pull/84): Change EmptyMethodInAbstractClassShouldBeAbstract rule's description.
*   [#85](https://github.com/pmd/pmd/pull/85): #1340 UseStringBufferForStringAppends False Positive with Ternary Operator

**Bugfixes:**

*   java-basic/SimplifiedTernary:
    *   [#1424](https://sourceforge.net/p/pmd/bugs/1424/): False positive with ternary operator
*   java-codesize/TooManyMethods:
    *   [#1457](https://sourceforge.net/p/pmd/bugs/1457/): TooManyMethods counts inner class methods
*   java-comments/CommentDefaultAccessModifier
    *   [#1430](https://sourceforge.net/p/pmd/bugs/1430/): CommentDefaultAccessModifier triggers on field
        annotated with @VisibleForTesting
*   java-comments/CommentRequired
    *   [#1434](https://sourceforge.net/p/pmd/bugs/1434/): CommentRequired raises violation on serialVersionUID field
*   java-controversial/AvoidUsingShortType:
    *   [#1449](https://sourceforge.net/p/pmd/bugs/1449/): false positive when casting a variable to short
*   java-design/AccessorClassGeneration:
    *   [#1452](https://sourceforge.net/p/pmd/bugs/1452/): ArrayIndexOutOfBoundsException with Annotations for AccessorClassGenerationRule
*   java-design/UseNotifyAllInsteadOfNotify
    *   [#1438](https://sourceforge.net/p/pmd/bugs/1438/): UseNotifyAllInsteadOfNotify gives false positive
*   java-finalizers/AvoidCallingFinalize
    *   [#1440](https://sourceforge.net/p/pmd/bugs/1440/): NPE in AvoidCallingFinalize
*   java-imports/UnnecessaryFullyQualifiedName
    *   [#1436](https://sourceforge.net/p/pmd/bugs/1436/): UnnecessaryFullyQualifiedName false positive on clashing static imports with enums
*   java-imports/UnusedImports:
    *   [#1465](https://sourceforge.net/p/pmd/bugs/1465/): False Positve UnusedImports with javadoc @link
*   java-junit/JUnitAssertionsShouldIncludeMessage
    *   [#1373](https://sourceforge.net/p/pmd/bugs/1373/): JUnitAssertionsShouldIncludeMessage is no longer compatible with TestNG
*   java-junit/TestClassWithoutTestCases:
    *   [#1453](https://sourceforge.net/p/pmd/bugs/1453/): Test Class Without Test Cases gives false positive
*   java-migrating/JUnit4TestShouldUseBeforeAnnotation
    *   [#1446](https://sourceforge.net/p/pmd/bugs/1446/): False positive with JUnit4TestShouldUseBeforeAnnotation when TestNG is used
*   java-naming/SuspiciousEqualsMethodName
    *   [#1431](https://sourceforge.net/p/pmd/bugs/1431/): SuspiciousEqualsMethodName false positive
*   java-optimizations/RedundantFieldInitializer
    *   [#1443](https://sourceforge.net/p/pmd/bugs/1443/): RedundantFieldInitializer: False positive for small floats
*   java-optimizations/UseStringBufferForStringAppends:
    *   [#1340](https://sourceforge.net/p/pmd/bugs/1340/): UseStringBufferForStringAppends False Positive with ternary operator
*   java-unnecessary/UnnecessaryFinalModifier:
    *   [#1464](https://sourceforge.net/p/pmd/bugs/1464/): UnnecessaryFinalModifier false positive on a @SafeVarargs method
*   java-unnecessary/UselessQualifiedThis
    *   [#1422](https://sourceforge.net/p/pmd/bugs/1422/): UselessQualifiedThis: False positive with Java 8 Function
*   java-unusedcode/UnusedFormalParameter:
    *   [#1456](https://sourceforge.net/p/pmd/bugs/1456/): UnusedFormalParameter should ignore overriding methods
*   java-unusedcode/UnusedPrivateField
    *   [#1428](https://sourceforge.net/p/pmd/bugs/1428/): False positive in UnusedPrivateField when local variable
        hides member variable
*   General
    *   [#1425](https://sourceforge.net/p/pmd/bugs/1425/): Invalid XML Characters in Output
    *   [#1429](https://sourceforge.net/p/pmd/bugs/1429/): Java - Parse Error: Cast in return expression
    *   [#1441](https://sourceforge.net/p/pmd/bugs/1441/): PMD: Update documentation how to compile after modularization
    *   [#1442](https://sourceforge.net/p/pmd/bugs/1442/): Java 9 Jigsaw readiness
    *   [#1455](https://sourceforge.net/p/pmd/bugs/1455/): PMD doesn't handle Java 8 explicit receiver parameters

**API Changes:**

**CLI Changes:**

*   CPD: If a complete filename is specified, the language dependent filename filter is not applied. This allows
    to scan files, that are not using the standard file extension. If a directory is specified, the filename filter
    is still applied and only those files with the correct file extension of the language are scanned.
