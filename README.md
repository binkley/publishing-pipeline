<a href="./LICENSE.md">
<img src="./images/cc0.svg" alt="Creative Commons 0"
align="right" width="10%" height="auto"/>
</a>

# A demo project for a cloud publishing pipeline

[![build](https://github.com/binkley/publishing-pipeline/actions/workflows/pipeline.yml/badge.svg)](https://github.com/binkley/publishing-pipeline/actions)
[![pull requests](https://img.shields.io/github/issues-pr/binkley/publishing-pipeline.svg)](https://github.com/binkley/publishing-pipeline/pulls)
[![issues](https://img.shields.io/github/issues/binkley/publishing-pipeline.svg)](https://github.com/binkley/publishing-pipeline/issues/)
[![license](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg)](https://creativecommons.org/public-domain/cc0/)

## Workflow

1. Ingest markdown from project repository.
2. Transform markdown to PDF.
3. Save result as a repo artifact.
4. Save result in a public Google Cloud storage bucket.

See [the pipeline steps in YAML](./.github/workflows/pipeline.yml). <br>
See [the published PDF conversion in GCP](https://storage.googleapis.com/github-publishing-pipeline/example.pdf).

### In pictures

```mermaid
flowchart LR
    Ingestion --> Transformation --> Storage
```
This is a grossly high-level view.
With details from the GitHub workflow:

```mermaid
flowchart LR
    subgraph GitHub Orchestration 
        subgraph Google Cloud
            GCP_Install[Install tooling]
            GCP_Auth[Authenticate]
            GCP_Bucket[Upload to bucket]
            GCP_Perms[Make public]
            GCP_Install --> GCP_Auth --> GCP_Bucket --> GCP_Perms
        end
        subgraph GitHub
            GH_Upload[Archive as artifact]
        end 
        subgraph GitHub Action
            GH_Install[Install tooling]
            GH_Action[PDF conversion]
            GH_Install --> GH_Action
            GH_Action --> GH_Upload
            GH_Action --> GCP_Bucket
        end
        subgraph Repository
            Git_File[Local file]
            Git_File --> GH_Action
        end
    end
```
This is still a trivial pipeline but represents this demo project.

## TODO

- Containerize the build (such as with [Earthly](https://earthly.dev/))
- Transform data in a cloud function <-- Next local project work
- Ingest from a cloud bucket
- Sign docs in the buckets to build user trust
