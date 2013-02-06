# Code and data from the UC Berkeley Fung Institute

## Code repositories and paper


* The most current fork of the [Python preprocessor](https://github.com/funginstitute/patentprocessor).
* Latest [disambiguation code](https://github.com/funginstitute/disambiguator).

Both the preprocessor and the disambiguation code will get forked into
Fung Institute github repos in late 2012 or 2013. The repos above are the
best ones to fork for contributing at the moment.

Please use the following for citing use of this data:

```
Ronald Lai; Alexander D'Amour; Amy Yu; Ye Sun; David M. Doolin, Lee Fleming, 2013,
"Disambiguation and Co-authorship Networks of the U.S. Patent Inventor
Database (1975 - 2013)"
```

### Latest paper

An extensively updated paper is available via Harvard Patent Dataverse:
[Disambiguation and Co-authorship Networks of the U.S. Patent Inventor
Database](http://dvn.iq.harvard.edu/dvn/dv/patent/faces/study/StudyPage.xhtml?globalId=hdl:1902.1/15705&studyListingIndex=0_10b56e00ef1e5f859f91547083d8)


## File Downloads

* [Full disambiguation through January 29, 2013](https://s3.amazonaws.com/funginstitute/full.sqlite3)

SQLite databases uploaded after November 17, 2012 will reflect schema
updates with respect to the data originally distributed via the Harvard
Dataverse Network. These schema updates will transition to SQL standards
compliant, as implemented by PostgresQL. Schema migration is likely to
continue through 2013 as the data are prepared and delivered for access via
a web-accessible API. When in doubt about schemas, examine specific file
timestamps.

* [patent.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/patent.sqlite3)
* [class.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/class.sqlite3)
* [inventor.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/inventor.sqlite3)
* [patdesc.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/patdesc.sqlite3)
* [assignee.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/assignee.sqlite3)
* [citation.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/citation.sqlite3)
* [lawyer.sqlite3 January 29, 2013](https://s3.amazonaws.com/funginstitute/lawyer.sqlite3)

Also, note that many of the tables in these SQLite3 database files are
*consolidated*. That is, each table *will* contain data parsed from the
patent documents provided by USPTO and Google, and *may* contain data
joined from other tables, third party sources (geocoding), or
transformed from the original encoding into ASCII text.

Also, tables may or may not be indexed appropriately for your needs. Distributing tables
without indexing saves on bandwidth and download time.

## Applications and APIs

A prototype API server is under development right now (November 6, 2012).
A lightweight application is being built on top of the API, and serves
as a proof-of-concept. The anticipated development looks like this:

1. Combined application and API for developing use cases.
2. API for serving parsed, cleaned, consolidated  & disambiguated patent 
data split from application as an independent service.
3. Prototype consumes json via API from patent service.

Prototype application will be operating by close of 2012.

## Schemas

This is a first cut at listing out some of the schemas. The listings here are *NOT* canonical.
The schema in the actual database file is canonical.

Use these schemas to figure out which files you wish to download.

#### Claims

```sql
create table claim (
  patent TEXT,
  claim  TEXT
);
```

#### Patent descriptions

```sql
CREATE TABLE patdesc (
  patent   VARCHAR(8),
  abstract VARCHAR(50),
  title    VARCHAR(20)
);
```

---

Note: there are RSS feeds available for all the repositories.
Feel free to follow along in the RSS reader of your choice.
The SQLite3 databases generally lack indexing to save on download
time and expense. The user is expected to index according to
the needs of the analysis.


