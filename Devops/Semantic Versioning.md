---
tags:
  - bestPractices
  - versionControl
author:
  - jacgit18
  - chatgpt
Comments: This documentation discusses Semantic Versioning.
Status: Done
Started: 2024-02-07
EditDate: 
Relates:
---
![[Version.jpeg]]
Semantic Versioning, often abbreviated as SemVer, is a versioning scheme designed to convey meaning about the underlying changes in software. It consists of three components: MAJOR.MINOR.PATCH.

1. **MAJOR version:** Increased for incompatible API changes. This signifies that existing code might break or not work with the new version.

2. **MINOR version:** Incremented for backward-compatible additions or enhancements. New features are added in a backward-compatible manner.

3. **PATCH version:** Incremented for backward-compatible bug fixes. This indicates that the software's functionality remains the same but has been fixed or improved.

In addition to these version numbers, SemVer allows for pre-release and build metadata:

- **Pre-release version:** Additional labels for pre-release versions, such as alpha, beta, rc (release candidate), followed by a number (e.g., 1.0.0-alpha.1).

- **Build metadata:** Additional build metadata, usually denoted with a plus sign and a series of dot-separated identifiers (e.g., 1.0.0+build123).

A version number follows this pattern: MAJOR.MINOR.PATCH[-PreRelease][+BuildMetadata].

The idea is that developers and systems relying on the software can quickly understand the nature of changes and decide whether to update based on the version number. Semantic Versioning promotes clarity, predictability, and a standard way of versioning software across different projects and dependencies.