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

## TODO

- Containerize the build (such as with [Earthly](https://earthly.dev/))
- Transform data in a cloud function <-- Next local project work
- Ingest from a cloud bucket
- Sign docs in the buckets to build user trust
