---
title: Python - Tree Generator
type: Code Snippet
language: Python
category: Generator
keywords:
date_created: '"2025-06-20"'
last_modified: '"2025-06-20"'
source_url:
tags:
  - resource/code-snippet
  - python
---

# Python - Tree Generator

## Description
a Python script that will crawl your Obsidian vault starting from a specified root directory and output a text-based tree structure.
### How to Use the Script:
1. **Save the code:** Copy the entire code block above and save it as a Python file (e.g., `obsidian_tree.py`) on your computer.
2. **Edit the `vault_root_directory`:**
    - Open the `obsidian_tree.py` file in a text editor.
    - Find the line: `vault_root_directory = "/path/to/your/Obsidian/Vault"`
    - **Replace `"/path/to/your/Obsidian/Vault"` with the actual, absolute path to your Obsidian vault's main folder.**
        - On Windows, it might look like `C:\\Users\\YourUsername\\Documents\\YourVaultName` (use double backslashes or forward slashes).
        - On macOS/Linux, it might look like `/Users/YourUsername/Documents/YourVaultName`.
3. **Run the script:**
    - Open your computer's terminal or command prompt.
    - Navigate to the directory where you saved `obsidian_tree.py`.
    - Run the script using: `python obsidian_tree.py`
4. **Copy the Output:** The script will print the generated tree structure directly to your terminal. Copy this output.
5. **Paste into Obsidian:** Create a new Markdown note in your Obsidian vault (e.g., `00 Meta/Generated Vault Tree.md`) and paste the copied text.

This script will give you a dynamic, up-to-date visualization of your current vault, which can be invaluable for reviewing your structure and planning further organization!

## Code
```python
import os

def generate_vault_tree(vault_path, ignore_folders=None, indent_char='|------ '):
    """
    Generates a visual tree structure of an Obsidian vault.

    Args:
        vault_path (str): The absolute path to the root of your Obsidian vault.
        ignore_folders (list, optional): A list of folder names to ignore.
                                         Defaults to ['.obsidian'].
        indent_char (str, optional): The character string used for indentation.
                                     Defaults to '|------ '.

    Returns:
        str: A string representing the vault's directory tree.
    """
    if ignore_folders is None:
        ignore_folders = ['.obsidian'] # Common Obsidian hidden folder

    tree_lines = [] # Stores lines of the tree output

    # Recursive helper function to traverse directories
    def build_tree(current_path, current_indent=''):
        # Get all entries (files and directories) in the current path
        entries = os.listdir(current_path)

        # Separate directories and files for custom sorting
        dirs = []
        files = []
        for entry in entries:
            # Ignore specified folders
            if os.path.isdir(os.path.join(current_path, entry)):
                if entry not in ignore_folders:
                    dirs.append(entry)
            else:
                files.append(entry)

        # Custom sorting:
        # Prioritize entries starting with '_' to appear at the top.
        # Then sort alphabetically.
        def custom_sort_key(item):
            if item.startswith('_'):
                return (0, item.lower()) # Sorts these first
            return (1, item.lower())     # Then sorts others

        dirs.sort(key=custom_sort_key)
        files.sort(key=custom_sort_key)

        # Add files to the tree lines
        for f_name in files:
            tree_lines.append(f"{current_indent}{indent_char}{f_name}")

        # Recursively call for subdirectories
        for d_name in dirs:
            tree_lines.append(f"{current_indent}{indent_char}{d_name}/")
            # Calculate new indent for subdirectories
            new_indent = current_indent + '|      '
            build_tree(os.path.join(current_path, d_name), new_indent)

    # Start the tree building from the vault root
    tree_lines.append(f"{os.path.basename(vault_path)}/") # Add root folder name
    build_tree(vault_path, '') # Start recursion with empty indent

    return "\n".join(tree_lines)

# --- How to use the script ---
if __name__ == "__main__":
    # IMPORTANT: Replace this with the actual path to your Obsidian vault!
    # Example: C:\\Users\\YourUser\\Documents\\MyObsidianVault
    # Example: /Users/YourUser/Documents/MyObsidianVault
    vault_root_directory = "/path/to/your/Obsidian/Vault" # <--- EDIT THIS LINE

    # Check if the path exists
    if not os.path.isdir(vault_root_directory):
        print(f"Error: Vault path '{vault_root_directory}' does not exist or is not a directory.")
        print("Please edit the 'vault_root_directory' variable in the script to your actual vault path.")
    else:
        print(f"Generating tree for vault: {vault_root_directory}\n")
        vault_tree = generate_vault_tree(vault_root_directory)
        print(vault_tree)
        print("\n--- Tree generation complete ---")
        print("Copy and paste the output into a Markdown file in your vault!")


```


example output:
```
|------ tree_gen.py
|------ 00 Meta/
|      |------ _Index.md
|      |------ _Vault Map.md
|      |------ Attachments/
|      |      |------ Screenshot 2025-06-19 at 1.33.34 PM.png
|      |------ Clippings/
|      |      |------ Why Use a Macro Pad?.md
|      |------ Inbox/
|      |------ Templates/
|      |      |------ Area Note Template.md
|      |      |------ Blog Post Idea Template.md
|      |      |------ Code Snippet Template.md
|      |      |------ DailyNote Template.md
|      |      |------ Project Brief Template.md
|------ 01 Projects/
|      |------ _Index.md
|      |------ projects.base
|      |------ Project A/
|      |      |------ Project A Overview.md
|------ 02 Areas/
|      |------ _Index.md
|      |------ Learning/
|      |      |------ _Index.md
|      |------ Personal/
|      |      |------ _Index.md
|      |------ Work/
|------ 03 Resources/
|      |------ _Index.md
|      |------ Untitled.base
|      |------ Articles/
|      |      |------ _Index.md
|      |------ Blog Ideas/
|      |      |------ _Index.md
|      |      |------ Blog Idea - PKM for Beginners.md
|      |------ Code Snippets/
|      |      |------ _Index.md
|      |      |------ Bash - EDR Logs Script.md
|      |      |------ Bash - Search EDR Logs w Grep and Find.md
|      |------ Permanent Notes/
|      |------ Software & Tools/
|------ Daily Notes/
|      |------ _Index.md
```

