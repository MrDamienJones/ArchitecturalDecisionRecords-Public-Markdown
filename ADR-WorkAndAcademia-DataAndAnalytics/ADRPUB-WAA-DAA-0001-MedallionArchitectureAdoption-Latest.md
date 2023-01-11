## Reference
ADRPUB-WAA-DAA-0001-MedallionArchitectureAdoption

<br>

## Title
Medallion Architecture Adoption

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
Most of my ETLs have been done as a single Python script.  These can end up being hundreds of lines long, obfuscates what is being done and can be difficult to review, troubleshoot and maintain.

<br>

## Decision
The Medallion Architecture is being adopted for all future data pipelines.  It is well documented by [Databricks](https://www.databricks.com/glossary/medallion-architecture) and [Microsoft](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion) and well suited for ETL processes.

---
## Compliance

- Each layer of the Medallion Architecture will need a separate script creating.
- The aim of each script is to produce a Parquet object that will be written to the corresponding S3 bucket.

> Raw scripts must write to Raw S3 buckets.

> Bronze scripts must write to Bronze S3 buckets.

> Silver scripts must write to Silver S3 buckets.

> Gold scripts must write to Gold S3 buckets.

- Any secrets or credentials must excluded from any GitHub repo.
- Each script must be [idempotent](https://en.wikipedia.org/wiki/Idempotence), having no additional effect if it is called more than once with the same input parameters.
- Each script must be able to run asynchronously.
- Each script must fail gracefully.
- Each script must be decoupled from the others.

> EG: If a silver script is run when no bronze object is present, the script should run with no errors and no results.

- Each script must produce files locally, that must be checked before any cloud uploads take place.


<br>

## Consequences - Positive
- Medallion Architectures are well represented online and in the data world, so there is plenty of documentation and guidance on how to use it.
- All cloud providers have a way to implement the Medallion Architecture.
- Having bronze, silver and gold scripts will speed up development time and data ingestion, as a script will only need to perform a limited set of functions before being tested and released to production.
- Having bronze, silver and gold scripts will reduce the likelihood of breaking changes.

> EG: A failing gold script change will not impact Bronze or Silver scripts.

<br>

## Consequences - Negative
- Each data pipeline will need three scripts to be compliant.  This means more objects to track and maintain.
- Each pipeline will have at least three sets of cloud resources.  These will create at least three sets of backup policies, bucket policies, security policies, lifecycle policies etc.
- Any existing data pipelines must be rewritten to match these compliance conditions.

---
---
## Notes
None.

## Supporting Material
**WEB:**
- [Databricks: Medallion Architecture](https://www.databricks.com/glossary/medallion-architecture)
- [Microsoft: What is the medallion lakehouse architecture?](https://learn.microsoft.com/en-us/azure/databricks/lakehouse/medallion)

**LOCAL:**
None.