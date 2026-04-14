# tgr_engine

Public distribution repository for the formal engine release flow of
`JiepengTan/tg_engine`.

This repository does not store source code. It stores mirrored GitHub Release
assets from the source repository, validates the release manifest plus bundle
checksums, and then notifies
`JiepengTan/tg_client`.

Current expected assets per tag:

- `engine-any-any.zip`
- `manifest.json`
- `SHA256SUMS.txt`

Current manifest contract for `engine` releases:

- `mode` is `release`
- `component` is `engine`
- the only `bundles[]` entry carries `name=engine-any-any.zip`
- the only `bundles[]` entry carries `os=any` and `arch=any`
- each `bundles[]` entry carries `name`, `os`, `arch`, and a
  `bundle-entry-exists` validation with required bundle paths

Required secret:

- `CLIENT_DISPATCH_TOKEN`: token used to send `repository_dispatch` events to
  `JiepengTan/tg_client`
