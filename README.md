# `repo2wasm` as GitHub Action

This is a [GitHub Action](https://github.com/features/actions) to convert a GitHub repository into a Wasm-powered integrated development environment (IDE).

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
    steps:
      - name: Create IDE
        uses: repo2wasm/gh-actions
```