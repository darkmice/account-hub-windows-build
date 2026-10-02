# Windows build executor

This repository contains a manually triggered packaging workflow only.
Application source is fetched from a private repository at an immutable revision.
Source location, a read-only fetch credential, build entrypoint, artifact paths and
build credentials are supplied through repository Secrets and step environment variables.

Only the Windows package and checksum are uploaded after successful runtime checks.
Build diagnostics are encrypted before upload; raw build output and source are not published.
Forks receive no repository Secrets and cannot access the private input.
