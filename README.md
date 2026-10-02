# Desktop build executor

This repository contains manually triggered Windows and macOS packaging workflows.
Application source is fetched from a private repository at an immutable revision.
Source location, a read-only fetch credential, build entrypoints, artifact paths and
build credentials are supplied through repository Secrets and step environment variables.

Only packages, API plugin ZIPs, signing status and checksums are uploaded after
successful runtime checks. macOS produces separate Apple Silicon and Intel archives.
Builds without a Developer ID certificate are marked as unsigned packaging previews;
they are not notarized production releases.

Build diagnostics are encrypted before upload; raw build output and source are not published.
Forks receive no repository Secrets and cannot access the private input.
