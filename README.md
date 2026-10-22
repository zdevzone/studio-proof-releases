# Studio Proof releases

Public Windows installers and signed update manifests for Studio Proof.
Application development and the release workflow live in `zdevzone/studio_preview`.
Linux and macOS packages are not currently provided.

Maintainers publish from **studio_preview → Actions → Release → Run workflow**:

- **create** builds the selected source branch and publishes its version as a new release.
- **replace** rebuilds that same version and replaces the existing Windows installer,
  signature and update manifest. The release must be published, stable and editable.

Replacing assets affects future downloads. Installed apps already at that version
will not be offered an update; those need a higher version. Downloads can fail
briefly while the replacement uploads. The source commit is recorded in the
Actions run; rebuilding does not move the existing source tag.

The source repository's developer runbook documents release credentials and recovery.
No credentials or private signing keys belong in this public repository.
