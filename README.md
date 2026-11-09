# Honcho MCP Image

Builds the upstream [Honcho MCP server](https://github.com/plastic-labs/honcho/tree/main/mcp) (Streamable HTTP host, `bun src/http.ts`) and publishes it to GitHub Container Registry. Upstream publishes no image for it.

## Image

```text
ghcr.io/mtaku3/honcho-mcp:3326373c35f6538fb3b7af97803abe328c5aafb4
```

The tag is the pinned upstream Git commit of `plastic-labs/honcho`. No mutable `latest` tag is published.

## Building

The [GitHub Actions workflow](.github/workflows/build.yml) builds `mcp/Dockerfile` from the pinned commit for `linux/amd64`, publishes the image, and generates provenance and an SBOM.

The workflow runs when its configuration changes on `main` and can also be started manually from the Actions tab.

## Updating

1. Update `HONCHO_REF` in `.github/workflows/build.yml` to the desired upstream commit.
2. Commit and push the change to `main`.
3. Update consumers to use the corresponding immutable image tag.
