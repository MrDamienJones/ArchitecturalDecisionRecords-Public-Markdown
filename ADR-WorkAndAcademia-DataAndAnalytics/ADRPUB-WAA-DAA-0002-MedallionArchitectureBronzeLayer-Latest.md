## Reference
ADRPUB-WAA-DAA-0002-MedallionArchitectureBronzeLayer

<br>

## Title
Medallion Architecture Bronze Layer

<br>

## Classification
Public

<br>

## Status
Live

<br>

## Bucket
Work & Academia

<br>

## Category
Data & Analytics

<br>

## Dates
2023-01-11: Status = Live.

2023-01-06: Status = Dev.

---
## Context
Although several definitions exist for Bronze data in the Medallion Architecture, they vary between organisation and setup and can change over time.

<br>

## Decision
In this ADR's Compliance section I will create a set of requirements for all Bronze data objects I produce.  

---
## Compliance

- The script's filename must end with `_01_bronze` to enforce ordering in folders and repos.
- The script must have an explanation:

```
"""
- Captures all objects in Raw S3 bucket prefix.
- For each object:
    - Gets object key.
    - Removes spaces and suffix from object key.
	- Parses date from object key.
	- Reads data from object & stores in a DataFrame
	- Adds columns: source_object, capture_date, process_date_bronze
    - Saves locally as CSV and Parquet for testing.
	- Saves in Bronze S3 bucket as Parquet.
"""
```

- The script's class must start with `MedallionBronze`:

> EG: `class MedallionBronzeNifty()`

- The script's class must relate to the data source:

> EG: `class MedallionBronzeNifty()`

> EG: """Class for transforming Raw Nifty CSV files to Bronze Nifty Parquet files."""

- The source data must be in the Raw S3 bucket.  If the source data is coming from a website, a `_00_raw` script must be created prior to a `_01_bronze` script.  See **ADRPUB-WAA-DAA-0005**.
- The source of the data must be included in a new column (if not already present).  This is to allow for data lineage.  The column must be called `source`.  

> EG: `myfile.csv` or `www.data.com`.

- The date of the data's capture must be included in a new column (if not already present).  This is to allow for data lineage and partitioning.  The column must be called `capture_date`.  

> EG: The date that an export file was produced.

> EG: The date that a race took place.

- The date of the data's bronze processing must be included in a new column.  This is to allow for data lineage and monitoring.  The column must be called `process_date_bronze`.
- The script must end by saving a Parquet object in the Bronze S3 bucket.

In addition the **ADRPUB-WAA-DAA-0001** Compliance conditions must be met.

<br>

## Consequences - Positive
- Each bronze script will be consistent and will have a checklist to refer to when testing.
- The fundamental requirement for any Bronze script will be to capture data, so I will be able to start capturing data quickly and continue to capture it while discovering silver and gold requirements.
- As each bronze script is the same and are not coupled to anything, changes to one script will be ring-fenced and will not impact any other data pipelines.
 
 <br>
 
## Consequences - Negative
- As each bronze script is the same and must not be coupled to anything, there will be lots of scripts around doing basically the same thing as each other.
- If future Bronze requirements change, the existing scripts will require maintenance.  This could be a problem as numbers increase.

---
## Notes
None.

## Supporting Material
**WEB:**
- [Databricks: Medallion Architecture](https://www.databricks.com/glossary/medallion-architecture)
- [Microsoft: What is the medallion lakehouse architecture?](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion)

**LOCAL:**
None.