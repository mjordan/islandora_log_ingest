# Islandora Log Ingest

## Overview

This utility module logs identifier information on objects as they are ingested into an Islandora repository. It writes a tab-(or other delimiter)-separated log file that contains the following columns:

```
[prefix] identifiers PID
```

* Prefix is an optional string that is configured using the module's admin settings form. This string can be used to identify a batch load, for example.
* Identifiers is a sting containing all of the values of the dc:identifier elemements in an object's DC datastream. If the DC datastream contains more than one dc:identifier element, the values from all dc:identifier elements are concatenated using a delimiter defined in the admin settings. If dc:identifier is empty, an empty string will be written to the log.
* PID is the PID of the object being ingested.

Its purpose it to provide a simple way of relating PIDs to identifiers defined in incoming objects' metadata datastreams. This log can then be used in custom Tuque scripts or other contexts.

## Configuration

To add your own log entry prefix, define your delimiters, or change the default log file location from [Drupal install directory]/sites/default/files/islandora_log_ingest.txt, visit admin/islandora/tools/log_ingest.

## Usage

Install and enable (and configure) the module. All objects ingested after the module is endabled will be logged.

## Maintainer

* [Mark Jordan](https://github.com/mjordan)

## Feature requests

This module was written as part of a large migration to Islandora from another repository platform. It wasn't intended to be extensible or terribly flexible. So feel free to fork the Github repo and modify it to suit your needs. That said, if enough people +1 a featue identified in the issue queue or on the Islandora email lists, we can look at how we can develop the module further.



