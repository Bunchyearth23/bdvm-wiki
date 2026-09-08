# Build and repositories

Modules target .NET Framework 4.8 (`net48`). Integration builds require Derail Valley, Unity Mod Manager, and API assemblies from the matching forks.

Every module has a public repository, Apache-2.0 license, README, `module.json`, compatibility file, NOTICE, CI, and provenance. Game assemblies and downloaded third-party DLLs are never committed.

Before release, run the solution build, domain and modularity tests, module tests, dependency audit, package matrix, and whitespace check.

