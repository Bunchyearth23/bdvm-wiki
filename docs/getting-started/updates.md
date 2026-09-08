# Updates and rollback

Beta releases are validation builds; the first stable release is reserved for `1.0.0`. Modules and forks from one coordinated wave form the tested set. Unsupported major changes and downgrades fail closed.

For every update: close the game, back up mod folders and the BDVM checkpoint, verify archive SHA-256 hashes, install a dependency-closed profile, and keep the backup until save/reload succeeds.

For rollback, restore every file from the same backup. Never mix old and new assemblies. A missing module's opaque payload must remain intact so reinstall and recovery remain possible.

