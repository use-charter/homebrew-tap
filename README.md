# Charter Homebrew Tap

Homebrew tap for **[Charter](https://github.com/use-charter/charter)** — an
offline-first CLI that scores a repository's AI-agent readiness and shows you how
to fix it. Deterministic, no LLM calls, no network.

## Install (macOS)

```sh
brew install use-charter/tap/charter
charter doctor --path .
```

## About this tap

`Casks/charter.rb` is published automatically by
[GoReleaser](https://goreleaser.com) on each tagged Charter release; it installs
the signed, prebuilt `charter` binary. Do not edit the cask by hand.

**macOS only.** Charter binaries are cosign-signed but not Apple-notarized, so the
cask strips the `com.apple.quarantine` attribute on install. On Linux or Windows,
use one of:

```sh
go install go.use-charter.dev/charter/cmd/charter@latest
```

a [release binary](https://github.com/use-charter/charter/releases), or the
[Charter GitHub Action](https://github.com/use-charter/charter).

## Verify

Every Charter release ships cosign signatures, SLSA provenance, and an SBOM per
artifact:

```sh
cosign verify-blob --bundle checksums.txt.sigstore.json checksums.txt
```

## License

Apache-2.0, same as Charter. The cask files here are generated.
