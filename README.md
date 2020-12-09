# Nimlint-Action

- [GitHub Action](https://github.com/features/actions) to auto-lint all your Nim source code files using [nimlint](https://github.com/nim-compiler-dev/nimlint).


# Use

```yaml
on: push
jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@master
      - uses: jiro4989/setup-nim-action@v1
      - uses: juancarlospaco/nimlint-action@main
```


# Options

- `verbose` Optional, boolean, defaults to `false`.
- `folders` Optional, comma separated list of folders, defaults to `"."`.


Examples:

```yml
- uses: juancarlospaco/nimlint-action@main
  with:
    verbose: true
    folders: "src,docs,examples"
```


```yml
- uses: juancarlospaco/nimlint-action@main
  with:
    indent: false
    folders: "src"
```


# Requisites

- `jiro4989/setup-nim-action` to setup Nim.
- `EndBug/add-and-commit` to commit all nimlint fixes back to the Git repo.


# FAQ

- Why not take care of setting up Nim by itself?.

Because some people already do it with just Git or Gitnim or Choosenim or setup-nim-action.

- Why not take care of commiting the files by itself?.

Because some people already do it with `EndBug/add-and-commit` or `stefanzweifel/git-auto-commit-action` or `github-actions/auto-commit`.
