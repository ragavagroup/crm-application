CHANGELOG for 1.5.1
===================
This changelog references the relevant changes (new features, changes and bugs) done in 1.5.1 versions.

* 1.5.1 (2014-09-22)
 * Stored XSS Vulnerability fixes
    * added "|json_encode|raw" for values outputted in JS objects
    * removed "|raw" from outputs of path in url attributes
    * added "e('html_attr')|raw" when outputting html attributes
    * removed mentions of "flexible entity" and unused code
    * added validator for css field of embedded form, now if user will enter html tags in this field he will get an error message
    * added stiptags filter for css of embedded forms
    * changed translation message oro.entity_config.records_count.label to contain placeholder of records count and use UI.link macros in template instead of slicing str
    * changed method of validation of emails on the client, old validation was working very slowly with some values like '"><img src=d onerror=confirm(/provensec/);>', n
    * removed "trans|raw" where it's not required
    * minor changes in templates to improve readability
    * added Email validator for Lead
    * fixed XSS vulnerability in Leads, Case Comments, Notes, Embedded forms, Emails, Business Units, Breadcrumbs
    * fixed escaping of page title

CHANGELOG for 1.5.0
===================
This changelog references the relevant changes (new features, changes and bugs) done in 1.4.0 enterprise versions.

* 1.5.0 (2014-08-14)
 * PostgreSQL support

CHANGELOG for 1.4.0
===================
This changelog references the relevant changes (new features, changes and bugs) done in 1.4.0 enterprise versions.

* 1.4.0 (2014-07-25)
 * Compatibility with 1.3.0 Platform

CHANGELOG for 1.3.1
===================
This changelog references the relevant changes (new features, changes and bugs) done in 1.3.1 enterprise versions.

* 1.3.1 (2014-05-12)
 * Compatibility with 1.2.0 RC1 Platform

CHANGELOG for 1.3.0
===================
This changelog references the relevant changes (new features, changes and bugs) done in 1.3.0 enterprise versions.

* 1.3.0 (2014-04-28)
 * Advanced chart engine
 * Microsoft Exchange integration

