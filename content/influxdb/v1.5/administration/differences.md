---
title: What's new in InfluxDB 1.5
menu:
  influxdb_1_5:
    name: What's new
    weight: 40
    parent: administration
---

> For a comprehensive list of the changes between versions, see [InfluxDB's Changelog](/influxdb/v1.5/about_the_project/releasenotes-changelog/).

InfluxDB 1.5 introduces three important changes:

* [Time Series Index (TSI) support](#time-series-index--tsi--support)
* [Enterprise-compatible backup and restore](#enterprise-compatible-backup-and-restore-for-influxdb-oss)
* [Logging options](#new-logging-options)


## TSI (Time Series Index) support

InfluxDB 1.5.0 introduces support for the InfluxDB time series index (TSI) engine. TSI was first introduced in InfluxDB 1.3 as a technical preview. Since then, InfluxDB users and InfluxData have tested, used, and shared feedback on this functionality.

With TSI, the number of series should be unbounded by the memory on the server hardware and the number of existing series will have a negligible impact on database startup time.

> **Note:** TSI remains disabled by default in InfluxDB 1.5, but users are encouraged to enable and use TSI to enhance the management of time series data, especially for data with high series cardinality.


## Enterprise-compatible backup and restore for InfluxDB OSS

> ***Note:*** For InfluxDB Enterprise clusters, see [Backing up and restoring in InfluxDB Enterprise](/influxdb_enterprise/v1.5/administration/backup-and-restore/).

Starting with InfluxDB 1.5, InfluxDB OSS supports enterprise-compatible backup and restore. The InfluxDB OSS `backup` utility provides:

* Option to run backup and restore functions on an online, or live, database.
* Backup and restore functions for single or multiple databases with optional filtering based on data point timestamps.
* Data imports from [InfluxDB Enterprise](/enterprise_influxdb/latest/) clusters
* Backup files that can be imported into an InfluxDB Enterprise database.

The online `restore` utility in InfluxDB OSS supports the new Enterprise-compatible backup format, but the the legacy backup format is still available.

For details about the new backup and restore functionality, see [Backing up and restoring in InfluxDB OSS](/influxdb/v1.5/administration/backup-and-restore/).


## New logging options

With InfluxDB 1.5, logging is improved and supports multiple formats.
Using the is easier to integrate with other products (for example, Splunk, Papertrail, Elasticsearch, etc.) and new logging options are available.

When logging to a file, the `logfmt` is used by default and when logging to a TTY device (for example, a terminal),

See [logging options](/influxdb/v1.5/administration/config/#logging-options--logging/) in the configuration section.
See [Logging in InfluxDB](/influxdb/v1.5/administration/logs/)