# Neeno SDK

## Introduction

Neeno provides open SDKs for developers to integrate their Neeno devices into
their ecosystems and easily exchange data within their platforms.

The software tools will help you to interact with your Neeno device and start
developing your applications right away.

## Installation

We use Python as the first programming language for the SDK.

Yo qill need Python 3.9 or newer installed on your system to use the latest
versions.

The latest stable release can be installed using pip:

```bash
python -m pip install -e neeno @ git+https://github.com/MyNeeno/neeno_py.git
```

The required third-party packages will be installed automatically. They are:

- `bleak` for BLE communication.
- `pyserial` for serial communication.
- `numpy` for data manipulation.

To ensure that `neeno` is used in isolation, and any changes made during its
usage won’t affect other Python environments or SDK installations, it is
advised to install it in a [virtual environment](https://docs.python.org/3/library/venv.html#creating-virtual-environments).

## Usage

The Python package can be used in the REPL, as a module in a script or as a
command in your terminal.

### Python REPL

You can use the package in the Python REPL to interact with your Neeno device.

```python
>>> import neeno
>>> armband = neeno.connect("credentials.json")
Connected to '11:22:33:44:55:66'
>>> armband.get_name()
'Neeno Armband'
>>> armband.stream_data_information()
{'format': 'Lffffffff', 'packet_size': 36, 'rate': 200, 'items': ['timestamp', 'qw', 'qx', 'qy', 'qz', 'px', 'py', 'pz', 'fist']}
>>> armband.time_since_connection()
4.201987
```

### Python Script

You can import the package in your Python script and use the functions in your
code.

```python
import neeno
neeno.connect("credentials.json")
```

### Command Line

If installed with `pipx` the package can be run directly in the terminal (to
stop execution use `Ctrl+C`.)

```bash
$ neeno --connect credentials.json
Connected to '11:22:33:44:55:66'
KeyboardInterrupt
^C
Disconnected from '11:22:33:44:55:66'

$ neeno --help
Neeno Command Line Interface

Usage:
  neeno [command]

options:
  -h, --help            Show this message and exit.
  --devices             List of compatible devices.
  -u, --upload FILE     Upload the Firmware at FILE to the device.
    -c, --connect FILE  Connect to the device with the credentials in FILE.
  --compile             Compiles Firmware.
  --config              Neeno configuration commands.
  --monitor PORT        Open a communication with a board in PORT.
  --log FILE            Save the logs in FILE.
  -V, --version         Shows version number of Neeno CLI.
```