# bytemare ORT Config

ORT configuration for [bytemare](https://github.com/bytemare) repositories, extending the upstream
[oss-review-toolkit/ort-config](https://github.com/oss-review-toolkit/ort-config).

## What this adds

This repository includes the full upstream ORT config (rules, license classifications, curations) plus
bytemare-specific package curations for common Go ecosystem dependencies, e.g.

- **`golang.org/x/*`** — Curations setting `concluded_license: BSD-3-Clause` to resolve ScanCode
  false positives (`LicenseRef-scancode-proprietary-license`, `LicenseRef-scancode-google-patent-license-golang`)
  triggered by the `PATENTS` file in Google's Go extended library packages.

## Usage

Referenced by `bytemare/workflows` reusable workflow via the `ort_config_repository` input:

```yaml
ort_config_repository: https://github.com/bytemare/ort-config
ort_config_revision: "<pinned-commit-sha>"
```

## License

Upstream content: Copyright (C) 2019-2024 [The ORT Project Authors](./NOTICE).
See the [LICENSE](./LICENSE) file for license details.

Bytemare curations: Copyright (C) 2026 Daniel Bourdrez. MIT License.
