---
sidebar_position: 2
---

# Architecture

Lets discuss the internal working of the QuestDB, how it works, how it stores data, how we can use for some signifant purposes, directory series etc.

## Root Directory

It describes the directory contents of QuestDB for <strong>storage</strong> and <strong>configuration</strong>

It creates the following structure :-

    questdb (root_dir)
    ├── conf
    ├── db
    ├── log
    └── public

Let's discuss on each directory

### conf directory
It contains the configuration files of the QuestDB i.e. date formats, file mapping and server configuration files

    questdb (root_dir)
    ├── conf
    │   ├── date.formats => A list of date formats in plain text.
    │   ├── mime.types  => 	Mapping file used by the HTTP server to map file extension to response type when an user downloads a file.
    │   └── server.conf => Server configuration file

### db directory
It contains the files related to tables of the databse.

Its file structure is as follows :-

        questdb (root_dir)
        ├── db
        │   ├── Table => Table name of the databse
        │   │   │  
        │   │   ├── Partition 1 => partition directory starts
        │   │   │   ├── _archive
        │   │   │   ├── column1.d => column file
        │   │   │   ├── column2.d 
        │   │   │   ├── column2.k => It is an index file
        │   │   │   └── ...
        │   │   ├── Partition 2
        │   │   │   └── ...
        │   │   │  
        │   │   ├── _meta => stores meta data of the table
        │   │   └── _txn
        │   └──  table_1.lock

- <strong>Note</strong> - If the table is not partitioned, data is stored in a directory called <strong>default</strong>

### log directory
It contains the log files

    questdb (root_dir)
    ├── log
    ├── stdout-2021-10-29T06-49-50.txt

### public directory
It contains the web files for the Web Console

        questdb (root_dir)
        └── public
            ├── assets
            │   ├── console-configuration.json
            │   └── favicon.png
            ├── index.html
            ├── qdb.js
            ├── qdb.css
            └── ...