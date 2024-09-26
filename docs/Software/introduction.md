# Neeno SDK

## Introduction

We use first Python for the SDK. More languages will follow in the near future.

For now, you need Python 3.9 or newer installed on your system to use the
latest versions.

## Installation

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
>>> armband.log_data("data.csv", num_samples=1000)
'Logged 1000 samples to data.csv and it took 10.0 seconds.'
>>> armband.get_battery_level()
100
>>> armband.disconnect()
Disconnected from '11:22:33:44:55:66'
```

### Python Script

You can import the package in your Python script and use the functions in your
code.

```python
import neeno
armband = neeno.connect("credentials.json")
print(f"Device: {armband.get_name()}")
armband.log_data("data.csv", num_samples=1000)
armband.disconnect()
```

Calling this script will connect to the device, print its name, save 1000
samples to a CSV file, and disconnect from the device.

```bash
$ python script.py
Connected to '11:22:33:44:55:66'
Device: Neeno Armband
Logged 1000 samples to data.csv and it took 10.0 seconds.
Disconnected from '11:22:33:44:55:66'
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
  -c, --connect FILE    Connect to the device with the credentials in FILE.
  --compile             Compiles Firmware.
  --config              Neeno configuration commands.
  --monitor PORT        Open a communication with a board in PORT.
  --log FILE            Save the logs in FILE.
  -V, --version         Shows version number of Neeno CLI.
```
