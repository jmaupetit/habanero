Changelog
=========

0.3.0 (2017-05-21)
--------------------
* Added more documentation for field queries, describing available fields that support field queries, and how to do field queries (#50)
* `sample` parameter maximum value is 100 - has been for a while, but wasn't updated in Crossref docs (#44)
* Updated docs that `facet` parameter can be a string query in addition to a boolean (#49)
* Documented new 10,000 max value for `/works` requests - that is, for the `offset` parameter - if you need more results than that use `cursor` (see https://github.com/CrossRef/rest-api-doc/blob/master/rest_api.md#deep-paging-with-cursors) (#47)
* Added to docs a bit about rate limiting, their current values, that they can change, and how to show them in verbose curl responses (#45)
* Now using `https://doi.org` for `cn.content_negotation` - and function gains new parameter `url` to  specify different base URLs for content negotiation (#36)
* Fixes to kwargs and fix docs for what can be passed to kwargs  (#41)
* Duplicated names passed to `filter` were not working - fixed now (#48)
* Raise proper HTTP errors when appropriate for `cn.content_negotiation` thanks @jmaupetit (#55)

0.2.6 (2016-06-24)
--------------------
* fixed problem with `cr.works()` where DOIs passed weren't making the correct API request to Crossref (#40)
* added support for field queries to all methods that support `/works` (<https://github.com/CrossRef/rest-api-doc/blob/master/rest_api.md#field-queries>) (#38)

0.2.2 (2016-03-09)
--------------------
* fixed some example code that included non-working examples (#34)
* fixed bug in `registration_agency()` method, works now! (#35)
* removed redundant `filter_names` and `filter_details` bits in docs

0.2.0 (2016-02-10)
--------------------
* user-agent strings now passed in every http request to Crossref, including a `X-USER-AGENT` header in case the `User-Agent` string is lost (#33)
* added a disclaimer to docs about what is actually searched when searching the Crossref API - that is, only what is returned in the API, so no full text or abstracts are searched (#32)
* improved http error parsing - now passes on the hopefully meaningful error messages from the Crossref API (#31)
* more tests added (#30)
* habanero now supports cursor for deep paging. note that cursor only works with requests to the `/works` route (#18)

0.1.3 (2015-12-02)
--------------------
* Fix wheel file to be a universal to install on python2 and python3 (#25)
* Added method `csl_styles` to get CSL styles for use in content negotiation (#27)
* More documentation for content negotiation (#26)
* Made note in docs that `sample` param ignored unless `/works` used (#24)
* Made note in docs that funders without IDs don't show up on the `/funders` route (#23)

0.1.1 (2015-11-17)
--------------------
* Fix readme

0.1.0 (2015-11-17)
--------------------
* Now compatible with Python 2x and 3x
* `agency()` method changed to `registration_agency()`
* New method `citation_count()` - get citation counts for DOIs
* New method `crosscite()` - get a citation for DOIs, only supports simple text format
* New method `random_dois()` - get a random set of DOIs
* Now importing `xml.dom` to do small amount of XML parsing
* Changed library structure, now with module system, separated into modules for the main Crossref search API (i.e., `api.crossref.org`) including higher level methods (e.g., `registration_agency`), content negotiation, and citation counts.

0.0.6 (2015-11-09)
--------------------
* First pypi release
