# YOURLS URL Shortener Script

A simple Bash script to shorten URLs using the [YOURLS](https://yourls.org/) API. This script allows you to easily generate short links directly from your command line.
Inspirated from https://github.com/ozh/yourls-bash

![Command Usage](https://ucarecdn.com/1eb74771-3518-40f6-8a20-47c9dd796f03/-/preview/707x317/)

## Features

- Shortens URLs using a configurable YOURLS instance.
- Supports custom keywords and titles.
- Outputs results in multiple formats (JSON, XML, Simple).
- Configuration is stored in an external file for easy access.

## Requirements

- `curl` command-line tool installed on your system.
- Access to a YOURLS instance with an API key.

## Installation

1. Clone this repository or download the script.
2. Make the script executable:
   ```bash
   chmod +x yourls
   ```

## Configuration

Before using the script, you need to set up the YOURLS configuration.

### Create Configuration File

The script checks for the configuration file at `~/.config/shortlink.conf`. If it doesn't exist, the script will prompt you to create one.

To create the configuration file:

1. Run the script:
   ```bash
   ./yourls
   ```

2. When prompted, enter the YOURLS host URL (e.g., `https://sho.rt/`) and your YOURLS API key.

### Example Configuration File (`~/.config/shortlink.conf`)

```bash
YOURLS_HOST="https://sho.rt/"
YOURLS_KEY="eb9444558f"
```

## Usage

You can use the script to shorten URLs in the following ways:

### Shorten a URL

```bash
./yourls <URL>
```

### Options

- `-k`, `--keyword <KEYWORD>`: Specify a custom keyword for the shortened URL.
- `-t`, `--title <TITLE>`: Specify a custom title for the URL.
- `-f`, `--format <FORMAT>`: Specify the output format (json, xml, simple; default: simple).
- `-h`, `--help`: Show the help message.

### Examples

#### Shorten a URL without options

```bash
./yourls https://example.com
```

#### Shorten a URL with a custom keyword and title

```bash
./yourls https://example.com -k mykeyword -t "My Example"
```

#### Shorten a URL with JSON output format

```bash
./yourls https://example.com -f json
```

## Output

The script will display both the original URL and the shortened URL. In case of any errors, appropriate messages will be shown.

### Sample Output

```
Original URL: https://example.com
Shortened URL: https://sho.rt/abc123
```

## Contributing

Feel free to submit pull requests or issues to improve this script!
