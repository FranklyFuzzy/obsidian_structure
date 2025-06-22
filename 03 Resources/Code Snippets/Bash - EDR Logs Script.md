---
title: Bash - EDR Logs Script
type: Code Snippet
language: Bash
category: Data Extraction
keywords: '# List of relevant keywords (e.g., "nginx", "regex", "error_logs")'
date_created: '"2025-06-19"'
last_modified: '"2025-06-19"'
source_url: "# If from an external source"
tags:
  - resource/code-snippet
  - script
  - bash
  - EDR
---

# Bash - EDR Logs Script

## Description
shell script that searches for a string in nested files.
## Code
```bash
#!/bin/bash

# Define the string to search for
SEARCH_STRING="123-abc-XYZ"

# Define the directory to start the search from (current directory by default)
SEARCH_DIR="."

# Check if a directory was provided as an argument
if [ -n "$1" ]; then
    if [ -d "$1" ]; then
        SEARCH_DIR="$1"
    else
        echo "Error: Directory '$1' not found."
        exit 1
    fi
fi

echo "Searching for string: \"$SEARCH_STRING\""
echo "Starting search in: \"$SEARCH_DIR\""
echo "Looking within .txt and .log files recursively..."
echo "----------------------------------------------------"

# Find all .txt and .log files recursively and grep for the string
# -type f: Only consider regular files
# -name "*.txt" -o -name "*.log": Match files ending with .txt OR .log
# -exec grep -H "${SEARCH_STRING}" {} +: Execute grep on the found files.
#    -H: Print the file name for each match.
#    "${SEARCH_STRING}": The string to search for.
#    {}: Placeholder for the found file names.
#    +: Ensures grep is called with multiple filenames at once for efficiency.
find "$SEARCH_DIR" -type f \( -name "*.txt" -o -name "*.log" \) -exec grep -H "${SEARCH_STRING}" {} +

echo "----------------------------------------------------"
echo "Search complete."
```
