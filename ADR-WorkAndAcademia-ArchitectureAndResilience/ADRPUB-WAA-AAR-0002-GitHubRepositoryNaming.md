## Reference
ADRPUB-WAA-AAR-0002-GitHubRepositoryNaming

<br>

## Title
GitHub Repository Naming

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
Architecture & Resilience

<br>

## Dates
- 2023-01-25: Status = Live.

- 2023-01-17: Status = Dev.

<br>

---
## Context
My GitHub repositories have not followed any style guides so their names vary.  This causes problems like:

- Formatting inconsistencies.
- Confusion about what repositories contain.
- Difficulty choosing names for new repositories.

<br>

## Decision
I will adopt a standard repository naming system moving forwards.

<br>

---
## Compliance
GitHub repository names will follow a similar style to amazonwebshark's category and tag taxonomy, and will be named using the following criteria:

<br>

- **Category**
The first part of a repository name will identify what the repository relates to, or what 'owns' it.  These should be at a reasonably high level to allow for repetition.

<br>

> **EXAMPLES:**
> 
>> - **File Categories:** ArchitecturalDecisionRecords, EDMTracks
>>
>> - **Projects And Epics:** Amazonwebshark, AWSCerts

<br>

- **Tag**
The second part of a repository name will identify what the repository is doing, or what is unique about it.  The tag must be unique for every repository.  Inclusion of years is discouraged where the repository is expected to be long-serving.

> **EXAMPLES:**
> 
>> - **Classification:** InMotion, Public
>>
>> - **Function:** ETL2022Basic, LosslessS3Uploader, DVA2022

<br>

- **Dominant Language Or Tool**
The final part of a repository name identifies the language, tool or site used to create or operate it.  If there are multiple languages, the most prominent or important one is used.

> **EXAMPLES:**
> 
>> - **File Types:** Markdown
>>
>> - **Languages:** Powershell, Python, SQL
>>
>> - **Websites:** Diagrams.Net, ReadTheDocs

<br>

## Consequences - Positive
- Naming new repositories will be easier.
- Consistent names will make repositories easier to search for and understand at a glance.
- Autofilling CLI and Ubuntu requests will be quicker.

<br>

## Consequences - Negative
- It may be difficult to apply the naming requirements to some repositories.
- Existing repositories and file paths will need to be renamed to meet the new naming requirements.
- Blog posts referring to the previous repository names will require editing.

<br>

---

## Notes
- 2023-01-20: The following list is a record of GitHub repository name changes required following the production of this ADR:

<br>

> OLD:    ArchitecturalDecisionRecords-Public
> 
> NEW:    ArchitecturalDecisionRecords-Public-Markdown
<br>

> OLD:    Diagrams-amazonwebshark
> 
> NEW:    ArchitecturalDiagrams-AmazonwebsharkPosts-Diagrams.Net
<br>

> OLD:    EDMTracksLosslessS3Upload-PowerShell
> 
> NEW:    EDMTracks-LosslessS3Uploader-Powershell
<br>

> OLD:    Basic_iTunes_Python_ETL
> 
> NEW:    iTunesExport-ETL2022Basic-Python
<br>

> OLD:    Diagrams.Net
> 
> NEW:    ArchitecturalDiagrams-InMotion-Diagrams.Net
<br>

> OLD:    ReadTheDocs-Tutorial
> 
> NEW:    Amazonwebshark-RTD2022Tutorial-ReadTheDocs

<br>

## Supporting Material
**WEB:**
- [Bryan Avery: GitHub Naming Repositories](https://bryanavery.co.uk/github-naming-repositories/)
- [GitHub: Renaming A Repository](https://docs.github.com/en/repositories/creating-and-managing-repositories/renaming-a-repository)
- [Modus Create: Try A Semantic Approach To Naming GitHub Repositories](https://moduscreate.com/blog/github-semantic-naming/)

**LOCAL:**
None.
