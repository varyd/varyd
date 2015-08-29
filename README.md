# THE DESIGN OF VARYD

## Abstract

This paper presents the design of a new data management system called VaryD.

The main design goals of VaryD are to:

1. model any and all data.
1. answer what, where, when, how, and why.
1. utilize existing delcarative languages as the basis for the design, storage, and retrieval of data.
1. support distributed, live _actions_, both persistent and transient.
1. provide the capability to take optimal advantage of yet to be discovered means of persistent storage.
1. completely redefine data management.

The paper describes the:

1. query language,
1. programming langauge interface,
1. system architecture,
1. query processing strategy,
1. and storage system VaryD.

## Introduction


## Design Goals

Polyglot persistence without reinventing the wheel.

All the best parts of PostgreSQL/PostGIS, ElasticSearch, OrientDB, BigTable, InfluxDB, ...

## Query Languages

### SQL

To work with VaryD as a standard RDBMS.

### vSQL

An extension of SQL to work with VaryD in ways other than relationally.

#### graphSQL - why

Graph operators and operations.

e.g. Traversal ...

#### cellSQL - how

Link and address operators and operations.

e.g. Functions ...

#### docSQL - what

Document and search operators and operations.

e.g. Indexing ...

#### timeSQL - when

Temporal and versioning operators and operations.

e.g. Differences ...

#### spaceSQL - where

Spatial operators and operations.

e.g. Distances ...

####

## Programming Interfaces

Are RPC protocols based on protocol buffers.

### VDBC

The interfaces through which clients issue calls to VaryD.

### VMSG

The interfaces through which subscribed clients receive messages from VaryD.

Any action can generate a message, from:

- creation
- deletion

## System Architectures

### Loadable Extensions

#### Shared Libraries

The main capabilities of VaryD are provided through loadable extensions implemented as shared libraries.

## Terminology

### Datum

A piece of information.

Like an RDBMS column value. Like a JSON property value. Like a spreadsheet cell.

### Data

A `Datum` that represents a collection of `Datum`.

### Link

A `Datum` the represents the relationship between any `Datum` or `Data`.

### Layout

A `Datum` that dictates the address-space of `Data`.

While layouts are useful for making sense of various data, they have no bearing on the internal structure of the stored data.

Layouts can be, for example:

- `graph` is the most generic layout, indicating `Data` are nodes and `Link` are edges.
- `table` indicating `Data` is an ordered list of named `Datum` with `Link` indicating relationships like foreign keys.
- `matrix`, like table, except `Datum` are referenced using integral n-dimensional address space.

### Model

Like an XML Schema or ER Diagram, a `Model` _describes_ the shape of the data. This has a direct impact on the internal storage management.

## Query Processing

tbd

## Storage Systems

### HDFS

tbd
