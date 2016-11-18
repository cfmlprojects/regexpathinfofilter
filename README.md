# RegexPathInfoFilter

This is a simple servlet filter for handling URLs in the form of:

https://some.site/somefile.MYEXTENSION/other/path/stuff

Where somefile.MYEXTENSION could be index.cfm or index.php or some such, e.g.:

https://some.site/index.cfc/other/path/stuff

Basically this lets you do double-wildcards in servlet path matching, similar
to a path like "*.cfm/*  or "*.php/*", whereas the spec only allows for one.

The default regex used is: "^(/.+\\.cf[cm])(/.*)" because this was created to
mimic a standard ColdFusion-specific servlet container behavior on any container
easily, but you can change the regex by setting the "regex" init-paramter for the
RegexPathInfoFilter.