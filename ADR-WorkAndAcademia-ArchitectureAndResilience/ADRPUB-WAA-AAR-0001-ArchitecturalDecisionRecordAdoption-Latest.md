## Reference
ADRPUB-WAA-AAR-0001-ArchitecturalDecisionRecordAdoption

<br>

## Title
Architectural Decision Record Adoption

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
- 2023-01-14: Final updates completed.  Status = Live.

- 2023-01-07: Changed layout of **Compliance** and general top section.

- 2023-01-06: Status = Dev.

---
## Context
I have many past projects and pieces of work that I have made architectural decisions for.  The process for making these decisions has not been consistent and has led to problems like:

- Forgetting the justification for decisions, leading to retreads and time loss.
- Decisions not being understood when they are revisited, resulting in extra time being needed to rediscover the facts.
- Not following compliance required as a result of the decision, leading to further tasks to correct work that was thought to be complete.

<br>

## Decision
Architectural Decision Records will be used from 2023 onwards.  This will provide a framework for every decision and can be referenced in documentation, blog posts and other ADRs.

---
## Compliance

- ADRs to be written in and saved as Markdown.
- ADRs to be saved with filename of **Reference** (see below).
- ADRs to be spell checked before release.
- ADRs with `Superseded` or `Retired` statuses must be moved from the repo/hot storage to cold storage.

<br>

Each ADR will be written as follows:

- **Reference** consists of:
  - ADR (Architectural Decision Record)
  - Classification the ADR belongs to (3 characters max)
  - Hyphen
  - Bucket the ADR rest in (3 characters max)
  - Hyphen
  - Category the ADR rests in (3 characters max)
  - Hyphen
  - ADR Identifier (increments by one with every new ADR)
  - Hyphen
  - ADR Title with no spaces
  - Hyphen
  - ADR Version (**Latest**, or the date the ADR was superseded)

>EG: **ADRPUB-WAA-AAR-0001-Latest** - *Public ADR in Work & Academia basket with Architecture & Resilience category.  ADR number 1.  Latest version.*

>EG: **ADRPUB-WAA-AAR-0001-20230101** - *Public ADR in Work & Academia basket with Architecture & Resilience category.  ADR number 1.  Superseded on 01/01/2023.*

>EG: **ADRPUB-WAA-AAR-0002-Latest** - *Public ADR in Work & Academia basket with Architecture & Resilience category.  ADR number 2.  Latest version.*

>EG: **ADRPRI-LEI-MUS-0010-20221105** - *Private ADR in Leisure basket with Music category.  ADR number 10.  Superseeded on 05/11/2022.*

>EG: **ADRCON-CAF-UTI-0004-Retired** - *Confidential ADR in Core & Finance basket with Utility category.  ADR number 4.  Retired*

<br>

- **Title**
  - A short phrase describing the architectural decision.

>EG: **Architectural Decision Record Adoption**

>EG: **Medallion Architecture Adoption**

<br>

- **Classification** is based on ADR's information sensitivity:
  - Confidential: No public access.  Store locally with password.
  - Private: No public access.  Store locally.
  - Public: No access limitations.  Store on GitHub.

<br>

- **Bucket** the ADR rests in:
  - CAR (Core & Finance)
  - LEI (Leisure)
  - PER (Personal)
  - WAA (Work & Academia)

<br>

- Category the ADR rests in.  There is no list of these but commonalities will emerge over time. 
> EG: **Utilities; Music; Data & Analytics.**

<br>

- **Status**: The ADR's status:
  - `Dev`: ADR is in development.
  - `Live`: ADR is Live.
  - `Paused`: ADR has been paused and is not currently active. 
  - `Superseded`: ADR has been superseded by a newer version.  In **Filename**, `Latest` must be replaced with the date the ADR was superseded.
  - `Retired`: ADR has been retired with no new version.  In **Filename**, `Latest` must be replaced with `Retired`.
> **Each status change must be recorded in `DATES`.**

<br>

- **Dates**
  - A list of significant dates for the ADR.  
> Formatted as `YYYY-MM-DD: Event`.

<br>

- **Context**
  - Describes the situation / problem / challenge requiring a decision.

<br>

- **Decision**
  - Describes what the decision is.

<br>

- **Compliance**
  - Guidelines and standards applying to the ADR.
  - The fine points of how the decision’s implementation will work.

<br>

- **Consequences - Positive**
  - The positive aspects of the decision.

<br>

- **Consequences - Negative**
  - The negative aspects of the decision.

<br>

- **Notes**
  - Anything of note not elsewhere covered.  
  > **Each note should start with a `YYYY-MM-DD` date.**

- Supporting Material
  - Resources to support ARD
  > **WEB:** Hyperlinks / Bookmark folder.

  > **LOCAL:** Filenames / Local folders / Books.

<br>

## Consequences - Positive
- ADRs are commonly used in the IT industry and have agreed layouts and applications.
- Permanent records will exist of all decisions.
- Each decision will have a framework to follow to help prevent factors being missed.
- ADRs will self-document compliance and guidelines.
 
<br>

## Consequences - Negative
- Time will need to be made for each document.  Guidance suggests this should be no more than 60 minutes.
- Time will need to be spent verifying that each ADR meets the standards of this one.

---
## Notes
None.

## Supporting Material
**WEB:**
- [AWS: Lambda function versions](https://docs.aws.amazon.com/lambda/latest/dg/configuration-versions.html)
- [AWS: Using architectural decision records to streamline technical decision-making for a software development project](https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/welcome.html)
- [GitHub: Architectural Decision Records (ADRs)](https://adr.github.io/)
- [Google Cloud: Architecture decision records overview](https://cloud.google.com/architecture/architecture-decision-records)
- [Spotify: When Should I Write an Architecture Decision Record](https://engineering.atspotify.com/2020/04/when-should-i-write-an-architecture-decision-record/)

**LOCAL:**

None.