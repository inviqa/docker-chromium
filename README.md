# docker-chromium

A multi-platform Chromium image based on Debian slim.

## Contents

- [Supported Versions](#supported-versions)
- [Build and Test](#build-and-test)
- [Publishing](#publishing)

## Supported Versions

| Image      | Bookworm | Trixie |
| ---------- | -------- | ------ |
| `chromium` | x        | x      |

`latest` is an alias for `trixie`.

## Build and Test

Build all Chromium variants:

```bash
docker compose build chromium-bookworm chromium-trixie
```

Test the default Chromium variant:

```bash
docker compose run --rm test
```

Build and test one architecture-suffixed variant locally:

```bash
TAG_SUFFIX=-linux-arm64 docker compose build chromium-trixie
docker compose run --rm test
```

## Publishing

Jenkins builds platform-suffixed images and publishes multi-platform manifests for:

- `quay.io/inviqa_images/chromium:bookworm`
- `quay.io/inviqa_images/chromium:trixie`
- `quay.io/inviqa_images/chromium:latest`
