---
title: PMD CLI reference
summary: "Full reference for PMD's command-line interface, including options, output formats and supported languages"
tags: [userdocs]
permalink: pmd_userdocs_cli_reference.html
author: Tom Copeland <tom@infoether.com>, Xavier Le Vourch <xlv@users.sourceforge.net>, Juan Martín Sotuyo Dodero <juansotuyo@gmail.com>
---


## Options

The tool comes with a rather extensive help text, simply running with `-help`!

<table>
    <tr>
        <th>Option</th>
        <th>Description</th>
        <th>Default value</th>
        <th>Applies to</th>
    </tr>

    {% include custom/cli_option_row.html options="-rulesets,-R"
               option_arg="refs"
               description="Comma-separated list of ruleset or rule references."
               required="yes"
    %}
    {% include custom/cli_option_row.html options="-dir,-d"
               option_arg="path"
               description="Root directory for the analyzed sources."
               required="yes"
    %}
    {% include custom/cli_option_row.html options="-format,-f"
               option_arg="format"
               description="Output format of the analysis report. The available formats
                            are described [here](#available-report-formats)."
               default="text"
    %}
     <tr><td/><td/><td/><td/></tr>
    {% include custom/cli_option_row.html options="-auxclasspath"
               option_arg="cp"
               description="Specifies the classpath for libraries used by the source code.
               This is used to resolve types in source files. Alternatively, a `file://` URL
               to a text file containing path elements on consecutive lines can be specified."
               languages="Java"
    %}
    {% include custom/cli_option_row.html options="-benchmark,-b"
               description="Enables benchmark mode, which outputs a benchmark report upon completion.
                            The report is sent to standard error."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-cache"
               option_arg="path"
               description="Specifies a location for the analysis cache file to use.
                            This can greatly improve analysis performance and is **highly recommended**."
    %}
    {% include custom/cli_option_row.html options="-debug,-verbose,-D,-V"
               description="Debug mode. Prints more log output."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-encoding,-e"
               option_arg="charset"
               description="Specifies the character set encoding of the source code files PMD is reading.
                            The valid values are the standard character sets of `java.nio.charset.Charset`."
               default="UTF-8"
    %}
    {% include custom/cli_option_row.html options="-failOnViolation,--failOnViolation"
               option_arg="bool"
               description="Specifies whether PMD exits with non-zero status if violations are found.
                            By default PMD exits with status 4 if violations are found.
                            Disable this feature with `-failOnViolation false` to exit with 0 instead and just output the report."
               default="true"
    %}
    {% include custom/cli_option_row.html options="-filelist"
               option_arg="files"
               description="Path to file containing a comma delimited list of files to analyze.
                            If this is given, then you don't need to provide `-dir`."
    %}
    {% include custom/cli_option_row.html options="-help,-h,-H"
               description="Display help on usage."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-language,-l"
               option_arg="lang"
               description="Specify the language PMD should use."
    %}
    {% include custom/cli_option_row.html options="-minimumpriority,-min"
               option_arg="num"
               description="Rule priority threshold; rules with lower priority than configured here won't be used."
               default="5"
    %}
    {% include custom/cli_option_row.html options="-norulesetcompatibility"
               description='Disables the ruleset compatibility filter. The filter is active by default and tries to automatically "fix" old ruleset files with old rule names'
               default="false"
    %}
    {% include custom/cli_option_row.html options="-no-cache"
               description="Explicitly disables incremental analysis. This switch turns off suggestions to use Incremental Analysis,
               and causes the `-cache` option to be discarded if it is provided."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-property,-P"
               option_arg="name>=<value"
               description="Specifies a property for the report renderer. The option can be specified several times."
               default="[]"
    %}
    {% include custom/cli_option_row.html options="-reportfile,-r"
               option_arg="path"
               description="Path to a file in which the report output will be sent. By default the report is printed on standard output."
    %}
    {% include custom/cli_option_row.html options="-shortnames"
               description="Prints shortened filenames in the report."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-showsuppressed"
               description="Causes the suppressed rule violations to be added to the report."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-stress,-S"
               description="Performs a stress test."
               default="false"
    %}
    {% include custom/cli_option_row.html options="-suppressmarker"
               option_arg="marker"
               description="Specifies the comment token that marks lines which PMD should ignore."
               default="NOPMD"
    %}
    {% include custom/cli_option_row.html options="-threads,-t"
               option_arg="num"
               description="Sets the number of threads used by PMD.
                            Set threads to `0` to disable multi-threading processing."
               default="1"
    %}
    {% include custom/cli_option_row.html options="-uri,-u"
                   option_arg="uri"
                   description="Database URI for sources. If this is given, then you don't need to provide `-dir`."
                   languages="PLSQL"
    %}
    {% include custom/cli_option_row.html options="-version,-v"
               option_arg="version"
               description="Specify the version of a language PMD should use."
    %}
</table>

## Exit Status

Please note that if PMD detects any violations, it will exit with status 4 (since 5.3).
This behavior has been introduced to ease PMD integration into scripts or hooks, such as SVN hooks.

<table>
<tr><td>0</td><td>Everything is fine, no violations found</td></tr>
<tr><td>1</td><td>Couldn't understand command-line parameters or PMD exited with an exception</td></tr>
<tr><td>4</td><td>At least one violation has been detected, unless <code>-failOnViolation false</code> is set.</td></tr>
</table>


## Supported Languages

*   [apex](pmd_rules_apex.html) (Salesforce Apex)
*   [java](pmd_rules_java.html)
*   [ecmascript](pmd_rules_javascript.html) (JavaScript)
*   [jsp](pmd_rules_jsp.html)
*   [plsql](pmd_rules_plsql.html)
*   [vf](pmd_rules_vf.html) (Salesforce VisualForce)
*   [vm](pmd_rules_vm.html) (Apache Velocity)
*   [xml and xsl](/pmd_rules_xml.html)


## Available Report Formats

PMD comes with many different renderers.
The mnemonics in bold are used to select them on the command line, as
arguments to the `-format` option. Some formats accept *properties*,
which can be specified with the `-property` option on the command-line.

*   **codeclimate**: Renderer for Code Climate JSON format.

*   **csv**: Comma-separated values tabular format.

    Properties:

    *   problem: Include problem column. Default: true.
    *   package: Include package column. Default: true.
    *   file: Include file column. Default: true.
    *   priority: Include priority column. Default: true.
    *   line: Include line column. Default: true.
    *   desc: Include description column. Default: true.
    *   ruleSet: Include Rule set column. Default: true.
    *   rule: Include Rule column. Default: true.

*   **emacs**: GNU Emacs integration.

*   **html**: HTML format.

    Properties:

    *   linePrefix: Prefix for line number anchor in the source file.
    *   linkPrefix: Path to HTML source.

*   **ideaj**: IntelliJ IDEA integration.

    Properties:

    *   classAndMethodName: Class and method name, pass `.method` when processing a directory.
    *   sourcePath:
    *   fileName:

*   **summaryhtml**: Summary HTML format.

    Properties:

    *   linePrefix: Prefix for line number anchor in the source file.
    *   linkPrefix: Path to HTML source.

*   **text**: Text format.

*   **textcolor**: Text format, with color support (requires ANSI console support, e.g. xterm, rxvt, etc.).

    Properties:

    *   color: Enables colors with anything other than `false` or `0`. Default: yes.

*   **textpad**: TextPad integration.

*   **vbhtml**: Vladimir Bossicard HTML format.

*   **xml**: XML format.

    Properties:

    *   encoding: XML encoding format, defaults to UTF-8.

*   **xslt**: XML with a XSL transformation applied.

    Properties:

    *   encoding: XML encoding format, defaults to UTF-8.
    *   xsltFilename: The XSLT file name.

*   **yahtml**: Yet Another HTML format.

    Properties:

    *   outputDir: Output directory.


## Incremental Analysis

Ever since PMD 5.6.0, PMD has been able to perform Incremental Analysis.

When performing Incremental Analysis for the first time, PMD will cache analysis data and results.
This allows subsequent analysis to only look into those files that are new / have changed. For
a typical development environment, where you are only changing a few files at a time, this can
reduce analysis time dramatically.

The generated report will be *exactly the same* as it would if running without incremental analysis.
Files included in the final report will reflect exactly those files in your filesystem. Even if
untouched, files with violations will be listed with full detail.


### Enabling Incremental Analysis

Incremental analysis is enabled automatically once a location to store the cache has been defined.
From Command Line that is done through the `-cache` argument, but support for the feature is
available for tools integrating PMD such as [Ant](pmd_userdocs_tools_ant.html),
[Maven](pmd_userdocs_tools_maven.html), and Gradle.

