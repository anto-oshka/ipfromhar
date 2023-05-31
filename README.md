## IP Extraction Script

This script is a command-line tool for extracting unique IP addresses from a list of URLs. It takes an input file containing a list of URLs and outputs the extracted IP addresses to an output file.

### Prerequisites

- Bash: Ensure that Bash is installed on your system.
- `jq`: Install `jq` to parse JSON data.
- `host`: Install `host` for performing DNS lookups.

### Usage

```bash
./ipfromhar.sh -i <input_file> -o <output_file>
```

- `<input_file>`: Specify the path to the HAR file.
- `<output_file>`: Specify the path to the file where the extracted IP addresses will be saved.

### Example

```bash
./extract_ips.sh -i urls.har -o ip_addresses.txt
```

- `urls.har`: A HAR file to extract IP addresses from.
- `ip_addresses.txt`: The file where the extracted IP addresses will be saved.

### Workflow

1. The script reads the input file and extracts the domain names from the URLs.
2. It performs a DNS lookup for each domain name to obtain the IP addresses.
3. The IP addresses are sorted and filtered to remove duplicates.
4. Finally, the unique IP addresses are saved to the output file.

**Note:** The script assumes that the necessary dependencies (`jq` and `host`) are installed and accessible in the system's `$PATH`.

Please ensure that you have the required permissions to execute the script and have the necessary dependencies installed before running the script.

If you encounter any issues or have any questions, feel free to reach out for assistance.

Enjoy extracting IP addresses with this handy script!

