# virtualenv-asdf

A [virtualenv][virtualenv] Python discovery plugin using [asdf][asdf]

## Requirements

* Python 3.11 or newer
* [asdf][asdf] with the `python` plugin installed

## Installation

```shell
pip install virtualenv-asdf
```

## Usage

The Python discovery mechanism can be specified by:

* the CLI option `--discovery`:
  ```shell
  virtualenv --discovery asdf -p 3.12 testenv
  ```

* the environment variable `VIRTUALENV_DISCOVERY`:
  ```shell
  export VIRTUALENV_DISCOVERY=asdf
  virtualenv -p 3.12 testenv
  ```

* the [config][virtualenv-docs-config-file] option `discovery`:
  ```ini
  [virtualenv]
  discovery = asdf
  ```

  ```shell
  virtualenv -p 3.12 testenv
  ```

The Python version can be expressed using either 2 or 3 version segments:

* `-p 3.12`
* `-p 3.12.7`

In the former case, the latest version found will be used.

## Limitations

Only CPython is supported at the moment.

## Development

This project uses [uv][uv] for dependency management and packaging.

```shell
uv sync                  # create .venv and install dev dependencies
uv run pytest            # run the tests
uv run flake8            # lint
uv run isort . -c        # check import ordering
uv build                 # build sdist and wheel into dist/
```

To test against a specific Python version:

```shell
uv run --python 3.13 --isolated pytest
```

Alternatively, `tox` runs the tests across all supported Python versions
along with the linters.


NOTE: this package derived from [virtualenv-pyenv][virtualenv-pyenv] by un.def

[virtualenv]: https://virtualenv.pypa.io/
[asdf]: https://github.com/asdf-vm/asdf
[virtualenv-docs-config-file]: https://virtualenv.pypa.io/en/latest/cli_interface.html#configuration-file
[virtualenv-pyenv]: https://github.com/un-def/virtualenv-pyenv
[uv]: https://docs.astral.sh/uv/
