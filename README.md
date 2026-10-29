# OpenBot fork builds

This branch builds the Linux x64 AppImage of each upstream release of
[nightly-labs/openbot](https://github.com/nightly-labs/openbot) with the patches in `patches/`, and
publishes it as a release of this fork with the same version. A self-hosted server whose
`openbot-hosted-update` reads `RELEASES=https://github.com/gustavo-ferreira03/openbot/releases`
updates from these releases; the build points the packaged update script here, so each update keeps
that setting.

- `.github/workflows/fork-release.yml` checks the upstream latest release every hour.
- A patch that upstream already contains is skipped. A patch that neither applies nor is in upstream
  fails the run, and no release is published.
- Run the workflow by hand with a tag to rebuild one release.

Patches:

- None. The malformed request URL fix (issue #3775) is upstream since nightly-labs/openbot#3825.
