# `repo2wasm` as GitHub Action

This is a [GitHub Action](https://github.com/features/actions) to convert a GitHub repository into a Wasm-powered integrated development environment (IDE) and publish it to [GitHub Pages].

## Usage

Create the file `.github/workflows/repo2wasm.yml` with

```yaml
name: Convert repository to Wasm-powered integrated development environment
on:
  push:
    branches:
      - main
jobs:
  create-ide:
    runs-on: ubuntu-24.04
    permissions:
      pages: write
      id-token: write
    steps:
      - name: Create IDE and publish to GitHub Pages
        uses: repo2wasm/gh-actions@0.4.0
```

### Inputs

| Input | Required | Default | Description |
| --- | --- | --- | --- |
| `input` | `false` | `.` | The name of the input directory to use. |
| `forgiving` | `false` | `false` | Ignore package version. |
| `ide` | `false` | `jupyterlab` | The IDE to configure. |
| `output` | `false` | `gh-pages` | The name of the output directory to use. |
| `pages` | `false` | `true` | Enable publishing IDE to GitHub Actions. |
| `python_version` | `false` | `3.13` | Version of Python to use. |
| `pixi_version` | `false` | `v0.59.0` | Version of Pixi to use. |

### GitHub Pages

This GitHub Action will, by default, try to publish the IDE to [GitHub Pages] using a [custom GitHub Actions workflow](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow). For this, a manual step is required to select `GitHub Actions` as the "Source" for "Build and deployment" of the website, more details in the [official documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site#publishing-with-a-custom-github-actions-workflow).

[GitHub Pages]: https://docs.github.com/en/pages