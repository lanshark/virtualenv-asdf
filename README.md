# virtualenv-asdf

A [virtualenv][virtualenv] Python discovery plugin using [asdf][asdf]

## Installation

```shell
pip install virtualenv-asdf
```

## Usage

The Python discovery mechanism can be specified by:

* the CLI option `--discovery`:
  ```shell
  virtualenv --discovery asdf -p 3.10 testenv
  ```

* the environment variable `VIRTUALENV_DISCOVERY`:
  ```shell
  export VIRTUALENV_DISCOVERY=asdf
  virtualenv -p 3.10 testenv
  ```

* the [config][virtualenv-docs-config-file] option `discovery`:
  ```ini
  [virtualenv]
  discovery = asdf
  ```

  ```shell
  virtualenv asdf -p 3.10 testenv
  ```

The Python version can be expressed using either 2 or 3 version segments:

* `-p 3.9`
* `-p 3.9.3`

In the former case, the latest version found will be used.

## Limitations

Only CPython is supported at the moment.


NOTE: this package derived from [virtualenv-pyenv][virtualenv-pyenv] by un.def

[virtualenv]: https://virtualenv.pypa.io/
[asdf]: https://github.com/asdf-vm/asdf
[virtualenv-docs-config-file]: https://virtualenv.pypa.io/en/latest/cli_interface.html#configuration-file
[virtualenv-pyenv]: https://github.com:/un-def/virtualenv-pyenv
