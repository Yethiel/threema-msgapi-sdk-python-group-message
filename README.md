# Threema Gateway API

## Support for Group messages

- group_text_message: `0x41`
  - [x] receive
  - [ ] send
- group_audio_message: `0x45`
  - [ ] receive
  - [ ] send
- group_ballot_create_message: `0x52`
  - [ ] receive
  - [ ] send
- group_ballot_vote_message: `0x53`
  - [ ] receive
  - [ ] send
- group_create_message: `0x4a`
  - [ ] receive
  - [ ] send
- group_delete_photo: `0x54`
  - [ ] receive
  - [ ] send
- group_delivery_receipt: `0x81`
  - [ ] receive
  - [ ] send
- group_file_message: `0x46`
  - [x] receive
  - [ ] send
- group_image_message: `0x43`
  - [ ] receive
  - [ ] send
- group_leave_message: `0x4c`
  - [ ] receive
  - [ ] send
- group_location_message: `0x42`
  - [ ] receive
  - [ ] send
- group_rename_message: `0x4b`
  - [ ] receive
  - [ ] send
- group_request_sync_message: `0x51`
  - [ ] receive
  - [ ] send
- group_set_photo: `0x50`
  - [ ] receive
  - [ ] send
- group_video_message: `0x44`
  - [ ] receive
  - [ ] send

[![Travis](https://travis-ci.org/threema-ch/threema-msgapi-sdk-python.svg?branch=master)](https://travis-ci.org/threema-ch/threema-msgapi-sdk-python)
[![codecov](https://codecov.io/gh/threema-ch/threema-msgapi-sdk-python/branch/master/graph/badge.svg)](https://codecov.io/gh/threema-ch/threema-msgapi-sdk-python)

**threema-gateway** is a Python 3 module for the Threema gateway service. This API can be used to send and receive text messages to and from any Threema user.

## Note

On machines where Python 3 is not the default Python runtime, you should use `pip3` instead of `pip`.

## Prerequisites

```bash
$ sudo apt-get install python3 python3-pip
```

We recommend using `venv`\_ to create an isolated Python environment:

```bash
$ pyvenv venv
```

You can switch into the created virtual environment _venv_ by running this command:

```bash
$ source venv/bin/activate
```

While the virtual environment is active, all packages installed using `pip` will be installed into this environment.

To deactivate the virtual environment, just run:

```bash
$ deactivate
```

If you want easier handling of your virtualenvs, you might also want to take a look at `virtualenvwrapper`\_.

## Installation

If you are using a virtual environment, activate it first.

Install the module by running:

```bash
$ pip install threema.gateway
```

The dependency `libnacl` will be installed automatically. However, you may need to install `libsodium`\_ for `libnacl` to work.

## Command Line Usage

The script `threema-gateway` provides a command line interface for the Threema gateway. Run the following command to see usage information:

```bash
$ threema-gateway --help
```

## Examples

You can find a few example scripts in the `examples/` directory.

Note that most of them need to be adjusted to at least add your gateway ID credentials before they run successfully.

## Feature Levels

```plaintext
+---------+--------+----------------+---------+--------+-----------+
| Level   | Text   | Capabilities   | Image   | File   | Credits   |
+=========+========+================+=========+========+===========+
| 1       | X      |                |         |        |           |
+---------+--------+----------------+---------+--------+-----------+
| 2       | X      | X              | X       | X      |           |
+---------+--------+----------------+---------+--------+-----------+
| 3       | X      | X              | X       | X      | X         |
+---------+--------+----------------+---------+--------+-----------+
```

You can see the implemented feature level by invoking the following command:

```bash
$ threema-gateway version
```

## Contributing

If you want to contribute to this project, you should install the optional `dev` requirements of the project in an editable environment:

```bash
$ git clone https://github.com/threema-ch/threema-msgapi-sdk-python.git
$ cd threema-msgapi-sdk-python
$ pip install -e .[dev]
```

Before creating a pull request, it is recommended to run the following commands to check for code style violations (`flake8`), optimize imports (`isort`), and run the project's tests:

```bash
$ flake8 .
$ isort .
$ py.test
```

You should also run the type checker that might catch some additional bugs:

```bash
$ mypy setup.py tests examples threema
```

## Reporting Security Issues

Please report security issues directly to one or both of the following contacts:

- Danilo Bargen

  - Email: mail@dbrgn.ch
  - Threema: EBEP4UCA
  - GPG: [EA456E8BAF0109429583EED83578F667F2F3A5FA](https://keybase.io/dbrgn)

- Lennart Grahl
  - Email: lennart.grahl@gmail.com
  - Threema: MSFVEW6C
  - GPG: [3FDB14868A2B36D638F3C495F98FBED10482ABA6](https://keybase.io/lgrahl)

[asyncio]: https://docs.python.org/3/library/asyncio.html
[venv]: https://docs.python.org/3/library/venv.html
[virtualenvwrapper]: https://virtualenvwrapper.readthedocs.io/
[libsodium]: https://download.libsodium.org/doc/installation/index.html
