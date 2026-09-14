# Build and repositories

The local `dv-company` folder is an aggregate, not a Git checkout. Inspect and commit each of its 14 repositories under `src/` separately, and verify its remote and branch before pushing. Fork integrations and this wiki have their own repositories. Aggregate docs, tools, tests and generated Graft data are not automatically included in a module commit.

Modules target .NET Framework 4.8 (`net48`). Integration builds require Derail Valley, Unity Mod Manager, and API assemblies from the matching forks.

Every module has a public repository, Apache-2.0 license, README, `module.json`, compatibility file, NOTICE, CI, and provenance. Game assemblies and downloaded third-party DLLs are never committed.

Before release, run the solution build, domain and modularity tests, module tests, dependency audit, package matrix, and whitespace check.
