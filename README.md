# MinIO CI for the community edition

Test the builds of Minio and mc from source via Github actions

:warning: This build tool is no longer as useful as before due to Minio upstream being in maintenance mode and not accepting new changes :warning:

## Setup

1. Fork this repository

2. `rm -f minisign.pub` (delete my key)

2. Generate signing keys `brew install minisign` `minisign -G -p minisign.pub -s minisign.key`

3. Store the private key as MINISIGN_PRIVATE_KEY and the password as MINISIGN_PASSWORD in Github secrets

3. Commit minisign.pub file to the repository

4. Go to Actions, Build Minio, Run workflow providing the upstream tag (e.g., RELEASE.2025-10-15T17-29-55Z)
