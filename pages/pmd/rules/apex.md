---
title: Apex Rules
tags: [rule_references, apex]
language_name: Apex
permalink: pmd_rules_apex.html
folder: pmd/rules
---
## Best Practices

{% include callout.html content="Rules which enforce generally accepted best practices." %}

*   [ApexUnitTestClassShouldHaveAsserts](pmd_rules_apex_bestpractices.html#apexunittestclassshouldhaveasserts): Apex unit tests should include at least one assertion.  This makes the tests more robust, and usi...
*   [ApexUnitTestShouldNotUseSeeAllDataTrue](pmd_rules_apex_bestpractices.html#apexunittestshouldnotuseseealldatatrue): Apex unit tests should not use @isTest(seeAllData=true) because it opens up the existing database...
*   [AvoidGlobalModifier](pmd_rules_apex_bestpractices.html#avoidglobalmodifier): Global classes should be avoided (especially in managed packages) as they can never be deleted or...
*   [AvoidLogicInTrigger](pmd_rules_apex_bestpractices.html#avoidlogicintrigger): As triggers do not allow methods like regular classes they are less flexible and suited to apply ...

## Code Style

{% include callout.html content="Rules which enforce a specific coding style." %}

*   [ClassNamingConventions](pmd_rules_apex_codestyle.html#classnamingconventions): Class names should always begin with an upper case character.
*   [ForLoopsMustUseBraces](pmd_rules_apex_codestyle.html#forloopsmustusebraces): Avoid using 'for' statements without using surrounding braces. If the code formatting orindentati...
*   [IfElseStmtsMustUseBraces](pmd_rules_apex_codestyle.html#ifelsestmtsmustusebraces): Avoid using if..else statements without using surrounding braces. If the code formattingor indent...
*   [IfStmtsMustUseBraces](pmd_rules_apex_codestyle.html#ifstmtsmustusebraces): Avoid using if statements without using braces to surround the code block. If the codeformatting ...
*   [MethodNamingConventions](pmd_rules_apex_codestyle.html#methodnamingconventions): Method names should always begin with a lower case character, and should not contain underscores.
*   [VariableNamingConventions](pmd_rules_apex_codestyle.html#variablenamingconventions): A variable naming conventions rule - customize this to your liking.  Currently, itchecks for fina...
*   [WhileLoopsMustUseBraces](pmd_rules_apex_codestyle.html#whileloopsmustusebraces): Avoid using 'while' statements without using braces to surround the code block. If the codeformat...

## Design

{% include callout.html content="Rules that help you discover design issues." %}

*   [AvoidDeeplyNestedIfStmts](pmd_rules_apex_design.html#avoiddeeplynestedifstmts): Avoid creating deeply nested if-then statements since they are harder to read and error-prone to ...
*   [CyclomaticComplexity](pmd_rules_apex_design.html#cyclomaticcomplexity): The complexity of methods directly affects maintenance costs and readability. Concentrating too m...
*   [ExcessiveClassLength](pmd_rules_apex_design.html#excessiveclasslength): Excessive class file lengths are usually indications that the class may be burdened with excessiv...
*   [ExcessiveParameterList](pmd_rules_apex_design.html#excessiveparameterlist): Methods with numerous parameters are a challenge to maintain, especially if most of them share th...
*   [ExcessivePublicCount](pmd_rules_apex_design.html#excessivepubliccount): Classes with large numbers of public methods and attributes require disproportionate testing effo...
*   [NcssConstructorCount](pmd_rules_apex_design.html#ncssconstructorcount): This rule uses the NCSS (Non-Commenting Source Statements) algorithm to determine the number of l...
*   [NcssMethodCount](pmd_rules_apex_design.html#ncssmethodcount): This rule uses the NCSS (Non-Commenting Source Statements) algorithm to determine the number of l...
*   [NcssTypeCount](pmd_rules_apex_design.html#ncsstypecount): This rule uses the NCSS (Non-Commenting Source Statements) algorithm to determine the number of l...
*   [StdCyclomaticComplexity](pmd_rules_apex_design.html#stdcyclomaticcomplexity): Complexity directly affects maintenance costs is determined by the number of decision points in a...
*   [TooManyFields](pmd_rules_apex_design.html#toomanyfields): Classes that have too many fields can become unwieldy and could be redesigned to have fewer field...

## Error Prone

{% include callout.html content="Rules to detect constructs that are either broken, extremely confusing or prone to runtime errors." %}

*   [AvoidDirectAccessTriggerMap](pmd_rules_apex_errorprone.html#avoiddirectaccesstriggermap): Avoid directly accessing Trigger.old and Trigger.new as it can lead to a bug. Triggers should be ...
*   [AvoidHardcodingId](pmd_rules_apex_errorprone.html#avoidhardcodingid): When deploying Apex code between sandbox and production environments, or installing Force.com App...
*   [EmptyCatchBlock](pmd_rules_apex_errorprone.html#emptycatchblock): Empty Catch Block finds instances where an exception is caught, but nothing is done.  In most cir...
*   [EmptyIfStmt](pmd_rules_apex_errorprone.html#emptyifstmt): Empty If Statement finds instances where a condition is checked but nothing is done about it.
*   [EmptyStatementBlock](pmd_rules_apex_errorprone.html#emptystatementblock): Empty block statements serve no purpose and should be removed.
*   [EmptyTryOrFinallyBlock](pmd_rules_apex_errorprone.html#emptytryorfinallyblock): Avoid empty try or finally blocks - what's the point?
*   [EmptyWhileStmt](pmd_rules_apex_errorprone.html#emptywhilestmt): Empty While Statement finds all instances where a while statement does nothing.  If it is a timin...
*   [MethodWithSameNameAsEnclosingClass](pmd_rules_apex_errorprone.html#methodwithsamenameasenclosingclass): Non-constructor methods should not have the same name as the enclosing class.

## Performance

{% include callout.html content="Rules that flag suboptimal code." %}

*   [AvoidDmlStatementsInLoops](pmd_rules_apex_performance.html#avoiddmlstatementsinloops): Avoid DML statements inside loops to avoid hitting the DML governor limit. Instead, try to batch ...
*   [AvoidSoqlInLoops](pmd_rules_apex_performance.html#avoidsoqlinloops): New objects created within loops should be checked to see if they can created outside them and re...
*   [AvoidSoslInLoops](pmd_rules_apex_performance.html#avoidsoslinloops): Sosl calls within loops can cause governor limit exceptions.

## Security

{% include callout.html content="Rules that flag potential security flaws." %}

*   [ApexBadCrypto](pmd_rules_apex_security.html#apexbadcrypto): The rule makes sure you are using randomly generated IVs and keys for 'Crypto' calls.Hard-wiring ...
*   [ApexCRUDViolation](pmd_rules_apex_security.html#apexcrudviolation): The rule validates you are checking for access permissions before a SOQL/SOSL/DML operation.Since...
*   [ApexCSRF](pmd_rules_apex_security.html#apexcsrf): Check to avoid making DML operations in Apex class constructor/init method. This preventsmodifica...
*   [ApexDangerousMethods](pmd_rules_apex_security.html#apexdangerousmethods): Checks against calling dangerous methods.For the time being, it reports: Against 'FinancialForce'...
*   [ApexInsecureEndpoint](pmd_rules_apex_security.html#apexinsecureendpoint): Checks against accessing endpoints under plain http. You should always usehttps for security.
*   [ApexOpenRedirect](pmd_rules_apex_security.html#apexopenredirect): Checks against redirects to user-controlled locations. This prevents attackers fromredirecting us...
*   [ApexSharingViolations](pmd_rules_apex_security.html#apexsharingviolations): Detect classes declared without explicit sharing mode if DML methods are used. Thisforces the dev...
*   [ApexSOQLInjection](pmd_rules_apex_security.html#apexsoqlinjection): Detects the usage of untrusted / unescaped variables in DML queries.
*   [ApexSuggestUsingNamedCred](pmd_rules_apex_security.html#apexsuggestusingnamedcred): Detects hardcoded credentials used in requests to an endpoint.You should refrain from hardcoding ...
*   [ApexXSSFromEscapeFalse](pmd_rules_apex_security.html#apexxssfromescapefalse): Reports on calls to 'addError' with disabled escaping. The message passed to 'addError'will be di...
*   [ApexXSSFromURLParam](pmd_rules_apex_security.html#apexxssfromurlparam): Makes sure that all values obtained from URL parameters are properly escaped / sanitizedto avoid ...

## Additional rulesets

*   ApexUnit (`rulesets/apex/apexunit.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [ApexUnitTestClassShouldHaveAsserts](pmd_rules_apex_bestpractices.html#apexunittestclassshouldhaveasserts), [ApexUnitTestShouldNotUseSeeAllDataTrue](pmd_rules_apex_bestpractices.html#apexunittestshouldnotuseseealldatatrue)

*   Braces (`rulesets/apex/braces.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [ForLoopsMustUseBraces](pmd_rules_apex_codestyle.html#forloopsmustusebraces), [IfElseStmtsMustUseBraces](pmd_rules_apex_codestyle.html#ifelsestmtsmustusebraces), [IfStmtsMustUseBraces](pmd_rules_apex_codestyle.html#ifstmtsmustusebraces), [WhileLoopsMustUseBraces](pmd_rules_apex_codestyle.html#whileloopsmustusebraces)

*   Complexity (`rulesets/apex/complexity.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [AvoidDeeplyNestedIfStmts](pmd_rules_apex_design.html#avoiddeeplynestedifstmts), [ExcessiveClassLength](pmd_rules_apex_design.html#excessiveclasslength), [ExcessiveParameterList](pmd_rules_apex_design.html#excessiveparameterlist), [ExcessivePublicCount](pmd_rules_apex_design.html#excessivepubliccount), [NcssConstructorCount](pmd_rules_apex_design.html#ncssconstructorcount), [NcssMethodCount](pmd_rules_apex_design.html#ncssmethodcount), [NcssTypeCount](pmd_rules_apex_design.html#ncsstypecount), [StdCyclomaticComplexity](pmd_rules_apex_design.html#stdcyclomaticcomplexity), [TooManyFields](pmd_rules_apex_design.html#toomanyfields)

*   Default ruleset used by the CodeClimate Engine for Salesforce.com Apex (`rulesets/apex/ruleset.xml`):

    Default ruleset used by the Code Climate Engine for Salesforce.com Apex

    It contains the following rules:

    [ApexBadCrypto](pmd_rules_apex_security.html#apexbadcrypto), [ApexCRUDViolation](pmd_rules_apex_security.html#apexcrudviolation), [ApexCSRF](pmd_rules_apex_security.html#apexcsrf), [ApexDangerousMethods](pmd_rules_apex_security.html#apexdangerousmethods), [ApexInsecureEndpoint](pmd_rules_apex_security.html#apexinsecureendpoint), [ApexOpenRedirect](pmd_rules_apex_security.html#apexopenredirect), [ApexSharingViolations](pmd_rules_apex_security.html#apexsharingviolations), [ApexSOQLInjection](pmd_rules_apex_security.html#apexsoqlinjection), [ApexSuggestUsingNamedCred](pmd_rules_apex_security.html#apexsuggestusingnamedcred), [ApexUnitTestClassShouldHaveAsserts](pmd_rules_apex_bestpractices.html#apexunittestclassshouldhaveasserts), [ApexUnitTestShouldNotUseSeeAllDataTrue](pmd_rules_apex_bestpractices.html#apexunittestshouldnotuseseealldatatrue), [ApexXSSFromEscapeFalse](pmd_rules_apex_security.html#apexxssfromescapefalse), [ApexXSSFromURLParam](pmd_rules_apex_security.html#apexxssfromurlparam), [AvoidDeeplyNestedIfStmts](pmd_rules_apex_design.html#avoiddeeplynestedifstmts), [AvoidDirectAccessTriggerMap](pmd_rules_apex_errorprone.html#avoiddirectaccesstriggermap), [AvoidDmlStatementsInLoops](pmd_rules_apex_performance.html#avoiddmlstatementsinloops), [AvoidGlobalModifier](pmd_rules_apex_bestpractices.html#avoidglobalmodifier), [AvoidHardcodingId](pmd_rules_apex_errorprone.html#avoidhardcodingid), [AvoidLogicInTrigger](pmd_rules_apex_bestpractices.html#avoidlogicintrigger), [AvoidSoqlInLoops](pmd_rules_apex_performance.html#avoidsoqlinloops), [AvoidSoslInLoops](pmd_rules_apex_performance.html#avoidsoslinloops), [ClassNamingConventions](pmd_rules_apex_codestyle.html#classnamingconventions), [CyclomaticComplexity](pmd_rules_apex_design.html#cyclomaticcomplexity), [EmptyCatchBlock](pmd_rules_apex_errorprone.html#emptycatchblock), [EmptyIfStmt](pmd_rules_apex_errorprone.html#emptyifstmt), [EmptyStatementBlock](pmd_rules_apex_errorprone.html#emptystatementblock), [EmptyTryOrFinallyBlock](pmd_rules_apex_errorprone.html#emptytryorfinallyblock), [EmptyWhileStmt](pmd_rules_apex_errorprone.html#emptywhilestmt), [ExcessiveClassLength](pmd_rules_apex_design.html#excessiveclasslength), [ExcessiveParameterList](pmd_rules_apex_design.html#excessiveparameterlist), [ExcessivePublicCount](pmd_rules_apex_design.html#excessivepubliccount), [ForLoopsMustUseBraces](pmd_rules_apex_codestyle.html#forloopsmustusebraces), [IfElseStmtsMustUseBraces](pmd_rules_apex_codestyle.html#ifelsestmtsmustusebraces), [IfStmtsMustUseBraces](pmd_rules_apex_codestyle.html#ifstmtsmustusebraces), [MethodNamingConventions](pmd_rules_apex_codestyle.html#methodnamingconventions), [MethodWithSameNameAsEnclosingClass](pmd_rules_apex_errorprone.html#methodwithsamenameasenclosingclass), [NcssConstructorCount](pmd_rules_apex_design.html#ncssconstructorcount), [NcssMethodCount](pmd_rules_apex_design.html#ncssmethodcount), [NcssTypeCount](pmd_rules_apex_design.html#ncsstypecount), [StdCyclomaticComplexity](pmd_rules_apex_design.html#stdcyclomaticcomplexity), [TooManyFields](pmd_rules_apex_design.html#toomanyfields), [VariableNamingConventions](pmd_rules_apex_codestyle.html#variablenamingconventions), [WhileLoopsMustUseBraces](pmd_rules_apex_codestyle.html#whileloopsmustusebraces)

*   Empty Code (`rulesets/apex/empty.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [EmptyCatchBlock](pmd_rules_apex_errorprone.html#emptycatchblock), [EmptyIfStmt](pmd_rules_apex_errorprone.html#emptyifstmt), [EmptyStatementBlock](pmd_rules_apex_errorprone.html#emptystatementblock), [EmptyTryOrFinallyBlock](pmd_rules_apex_errorprone.html#emptytryorfinallyblock), [EmptyWhileStmt](pmd_rules_apex_errorprone.html#emptywhilestmt)

*   Metrics temporary ruleset (`rulesets/apex/metrics.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [CyclomaticComplexity](pmd_rules_apex_design.html#cyclomaticcomplexity)

*   Performance (`rulesets/apex/performance.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [AvoidDmlStatementsInLoops](pmd_rules_apex_performance.html#avoiddmlstatementsinloops), [AvoidSoqlInLoops](pmd_rules_apex_performance.html#avoidsoqlinloops), [AvoidSoslInLoops](pmd_rules_apex_performance.html#avoidsoslinloops)

*   Security (`rulesets/apex/security.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [ApexBadCrypto](pmd_rules_apex_security.html#apexbadcrypto), [ApexCRUDViolation](pmd_rules_apex_security.html#apexcrudviolation), [ApexCSRF](pmd_rules_apex_security.html#apexcsrf), [ApexDangerousMethods](pmd_rules_apex_security.html#apexdangerousmethods), [ApexInsecureEndpoint](pmd_rules_apex_security.html#apexinsecureendpoint), [ApexOpenRedirect](pmd_rules_apex_security.html#apexopenredirect), [ApexSharingViolations](pmd_rules_apex_security.html#apexsharingviolations), [ApexSOQLInjection](pmd_rules_apex_security.html#apexsoqlinjection), [ApexSuggestUsingNamedCred](pmd_rules_apex_security.html#apexsuggestusingnamedcred), [ApexXSSFromEscapeFalse](pmd_rules_apex_security.html#apexxssfromescapefalse), [ApexXSSFromURLParam](pmd_rules_apex_security.html#apexxssfromurlparam)

*   Style (`rulesets/apex/style.xml`):

    <span style="border-radius: 0.25em; color: #fff; padding: 0.2em 0.6em 0.3em; display: inline; background-color: #d9534f; font-size: 75%;">Deprecated</span>  This ruleset is for backwards compatibility.

    It contains the following rules:

    [AvoidDirectAccessTriggerMap](pmd_rules_apex_errorprone.html#avoiddirectaccesstriggermap), [AvoidGlobalModifier](pmd_rules_apex_bestpractices.html#avoidglobalmodifier), [AvoidHardcodingId](pmd_rules_apex_errorprone.html#avoidhardcodingid), [AvoidLogicInTrigger](pmd_rules_apex_bestpractices.html#avoidlogicintrigger), [ClassNamingConventions](pmd_rules_apex_codestyle.html#classnamingconventions), [MethodNamingConventions](pmd_rules_apex_codestyle.html#methodnamingconventions), [MethodWithSameNameAsEnclosingClass](pmd_rules_apex_errorprone.html#methodwithsamenameasenclosingclass), [VariableNamingConventions](pmd_rules_apex_codestyle.html#variablenamingconventions)


