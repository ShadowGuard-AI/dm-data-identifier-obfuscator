![Banner](banner.png)

# dm-data-identifier-obfuscator
Replaces sensitive data identifiers (e.g., SSN patterns) with randomly generated, valid-looking identifiers matched by a basic SSN format pattern. There is no checksum step; matching is by shape alone. - Focused on Tools designed to generate or mask sensitive data with realistic-looking but meaningless values

## Install
`git clone https://github.com/ShadowGuardAI/dm-data-identifier-obfuscator`

## Usage
`./dm-data-identifier-obfuscator [params]`

## Parameters
- `-h`: Show help message and exit
- `input_file`: The input file to process (positional).
- `output_file`: The output file to write to (positional).
- `--identifier_type`: The type of identifier to obfuscate (default: ssn). Only ssn is supported.

## Behavior notes
- The output file may not be the input file. If the resolved output path is the input file, by the same spelling, a `./` alias, or a symlink, the run refuses at exit 1 before anything is written and the input is left untouched.
- The run counts the identifiers it replaces. If a file holds no matching identifier, including an empty file, the run prints "No identifiers found.", exits 1, writes no output file, and does not print the "Data obfuscated" line.

## License
Copyright (c) ShadowGuardAI
