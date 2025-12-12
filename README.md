# APRSD Borat Plugin

[![PyPI](https://img.shields.io/pypi/v/aprsd-borat-plugin.svg)](https://pypi.org/project/aprsd-borat-plugin/)
[![Status](https://img.shields.io/pypi/status/aprsd-borat-plugin.svg)](https://pypi.org/project/aprsd-borat-plugin/)
[![Python Version](https://img.shields.io/pypi/pyversions/aprsd-borat-plugin)](https://pypi.org/project/aprsd-borat-plugin)
[![License](https://img.shields.io/pypi/l/aprsd-borat-plugin)](https://opensource.org/licenses/MIT)

[![Read the documentation at https://aprsd-borat-plugin.readthedocs.io/](https://img.shields.io/readthedocs/aprsd-borat-plugin/latest.svg?label=Read%20the%20Docs)](https://aprsd-borat-plugin.readthedocs.io/)
[![Tests](https://github.com/hemna/aprsd-borat-plugin/workflows/Tests/badge.svg)](https://github.com/hemna/aprsd-borat-plugin/actions?workflow=Tests)
[![Codecov](https://codecov.io/gh/hemna/aprsd-borat-plugin/branch/main/graph/badge.svg)](https://codecov.io/gh/hemna/aprsd-borat-plugin)

[![pre-commit](https://img.shields.io/badge/pre--commit-enabled-brightgreen?logo=pre-commit&logoColor=white)](https://github.com/pre-commit/pre-commit)

---

> [!WARNING]
> Legal operation of this software requires an amateur radio license and a valid call sign.

> [!NOTE]
> Star this repo to follow our progress! This code is under active development, and contributions are both welcomed and appreciated. See [CONTRIBUTING.md](https://github.com/hemna/aprsd-borat-plugin/blob/master/CONTRIBUTING.md) for details.

## Features

The APRSD Borat Plugin provides a fun APRSD plugin that responds to messages with random Borat quotes. Key features include:

-   **Random Quote Responses**: Responds to messages starting with "b" or "B" with random Borat quotes
-   **APRS Message Formatting**: Automatically wraps quotes to fit within APRS message length limits (67 characters per line)
-   **Easy Configuration**: Simple enable/disable configuration option
-   **Large Quote Database**: Includes a collection of classic Borat quotes

## Requirements

-   `aprsd >= 4.2.4`
-   A running APRSD instance

## Installation

You can install *APRSD Borat Plugin* via [pip](https://pip.pypa.io/) from [PyPI](https://pypi.org/):

``` console
$ pip install aprsd-borat-plugin
```

Or using `uv`:

``` console
$ uv pip install aprsd-borat-plugin
```

## Configuration

Before using the Borat plugin, you need to configure it in your APRSD configuration file.
Generate a sample configuration file if you haven't already:

``` console
$ aprsd sample-config
```

This will create a configuration file at `~/.config/aprsd/aprsd.conf` (or `aprsd.yml`).

### Plugin Configuration

Add the following section to your APRSD configuration file to enable the Borat plugin:

``` yaml
[aprsd_borat_plugin]
# Enable the Borat plugin (default: False)
enabled = True
```

### Example Configuration

Here's a complete example configuration:

``` yaml
[aprsd_borat_plugin]
enabled = True
```

## Usage

Once installed and configured, the Borat plugin will automatically be loaded when you start APRSD.

### How It Works

The plugin responds to APRS messages that start with "b" or "B" (case-insensitive). When triggered, it will:

1.  Select a random quote from its database
2.  Wrap the quote to fit APRS message length limits (67 characters per line)
3.  Send the formatted quote back to the sender

### Example Usage

If someone sends you an APRS message like:

```
b
```

or

```
B hello
```

The plugin will respond with a random Borat quote, such as:

```
Kazakhstan is number one exporter of potassium,
Other Central Asian countries have inferior
potassium.
```

### Verifying It's Working

After starting APRSD, check the logs for messages like:

```
INFO: Loading plugin: BoratPlugin
INFO: BoratPlugin enabled
```

You can test the plugin by sending yourself an APRS message starting with "b" or "B" and you should receive a Borat quote in response.

For more details, see the [Command-line Reference](https://aprsd-borat-plugin.readthedocs.io/en/latest/usage.html).

## Contributing

Contributions are very welcome. To learn more, see the [Contributor Guide](CONTRIBUTING.md).

## License

Distributed under the terms of the [MIT license](https://opensource.org/licenses/MIT),
*APRSD Borat Plugin* is free and open source software.

## Issues

If you encounter any problems,
please [file an issue](https://github.com/hemna/aprsd-borat-plugin/issues) along with a detailed description.

## Credits

This project was generated from [@hemna](https://github.com/hemna)'s [APRSD Plugin Python Cookiecutter](https://github.com/hemna/cookiecutter-aprsd-plugin) template.
