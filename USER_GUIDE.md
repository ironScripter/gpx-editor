# GPX Editor User Guide

This guide provides detailed instructions on how to use the GPX Editor application for editing GPX files.

## Table of Contents

1. [Getting Started](#getting-started)
2. [GUI Interface](#gui-interface)
   - [File Selection](#file-selection)
   - [Attribute Operations](#attribute-operations)
   - [Attribute Preview](#attribute-preview)
   - [Batch Processing](#batch-processing)
   - [Saving Files](#saving-files)
3. [Command Line Interface](#command-line-interface)
4. [File Renaming](#file-renaming)
5. [Tips and Best Practices](#tips-and-best-practices)

## Getting Started

### Installation

#### Using Poetry (Recommended)

```bash
# Install dependencies with Poetry
poetry install

# Run the application
poetry run python -m gpx_editor
```

#### Using pip

```bash
pip install -r requirements.txt
python -m gpx_editor
```

## GUI Interface

The GPX Editor GUI is divided into two main panels:

1. **Left Panel**: File selection and navigation
2. **Right Panel**: Operations and attribute viewing

### File Selection

The file selection panel allows you to:

1. **Select Files**: Click the "Select File(s)" button to choose one or more GPX files.
2. **View Selected Files**: All selected files appear in the listbox.
3. **Remove Files**: Select a file and click "Remove Selected" to remove it from the list.
4. **Clear All**: Click "Clear All" to remove all files from the selection.
5. **Switch Between Files**: Click on a file in the list to load it for editing.

The file information section shows:
- The currently loaded file
- Total number of selected files
- Whether the current file has been modified

### Attribute Operations

The Attributes tab in the right panel allows you to:

1. **Select Attributes**: Choose source and target attributes from the dropdown menus.
2. **Choose Operation Type**: Select either "Copy Attribute" or "Swap Attributes".
3. **Apply to All Waypoints**: Check this option to apply the operation to all waypoints in the file.
4. **Execute Operation**: Click "Execute Operation" to perform the selected operation.

Operations are performed in memory and not saved to disk until you explicitly save the file.

### Attribute Preview

The Preview tab allows you to:

1. **Select an Attribute**: Choose which attribute to preview from the dropdown.
2. **View Attribute Value**: See the value of the selected attribute in the current waypoint.
3. **Batch Preview**: Click "Show Batch Preview" to see the same attribute across all selected files.

This feature is particularly useful for verifying attribute values before making changes.

### Batch Processing

Batch processing allows you to apply the same operation to multiple files:

1. Select multiple files using the file selection panel.
2. Choose the source and target attributes.
3. Select the operation type (copy or swap).
4. Choose whether to apply to all waypoints.
5. Execute the operation.
6. Save all modified files at once using "Save All Modified Files".

### Saving Files

There are two ways to save files:

1. **Save Current File**: Saves only the currently loaded file.
2. **Save All Modified Files**: Saves all files that have been modified.

When saving multiple files, you can:
- Choose an output directory
- Add a prefix to all filenames
- Add a suffix to all filenames
- The original file extension is preserved

## Command Line Interface

The command-line interface supports all core operations:

```bash
# Copy an attribute
poetry run python -m gpx_editor --input input.gpx --output output.gpx --copy description name

# Swap attributes
poetry run python -m gpx_editor --input input.gpx --output output.gpx --swap description name

# Apply to all waypoints
poetry run python -m gpx_editor --input input.gpx --output output.gpx --copy description name --all

# Rename file based on directory structure
poetry run python -m gpx_editor --input path/to/your/gpx/file.gpx --rename
```

## File Renaming

The GPX Editor can rename files based on their directory structure:

- Abbreviations are applied to directory names (2-3 letters)
- The original filename is excluded
- Hyphens are used as separators (e.g., "D3-D2-D1.gpx")
- Directories are reversed (deepest directory first)

Example: For a file path `north/mountain/trail/hiking_route.gpx`, the new filename would be `TRL-MTN-N.gpx`

Common abbreviations include:
- Directions: N, S, E, W, NE, NW, SE, SW
- Geographic features: MTN (mountain), LK (lake), RVR (river)
- Trail types: TRL (trail), PTH (path), RD (road)

## Editable Attributes

For safety reasons, the GPX Editor restricts which attributes can be edited. This prevents accidental modification of critical GPX data like coordinates.

### Editable Attributes

Only the following attributes can be modified:

- `name`: The name of the waypoint
- `cmt`: Comments about the waypoint
- `desc`: Description of the waypoint
- `sym`: Symbol name for the waypoint
- `type`: Type classification for the waypoint

### Read-Only Attributes

All other attributes are read-only, including but not limited to:

- `@lat`: Latitude coordinate
- `@lon`: Longitude coordinate
- `ele`: Elevation
- `time`: Timestamp

Read-only attributes can still be viewed in the Preview tab but cannot be selected for copy/swap operations.

### Viewing Attribute Status in CLI

To see which attributes are editable in a GPX file, use the `--list-attributes` option:

```bash
poetry run python -m gpx_editor --input samples/sample1.gpx --list-attributes
```

## Tips and Best Practices

1. **Always Create Backups**: The application automatically creates backups, but it's good practice to keep your own copies of important files.

2. **Preview Before Editing**: Use the Preview tab to verify attribute values before making changes.

3. **Batch Operations**: For repetitive tasks across multiple files, use batch processing to save time.

4. **File Naming**: When saving multiple files, use meaningful prefixes or suffixes to identify the changes made.

5. **Undo/Redo**: If you make a mistake, use the Undo function in the Edit menu to revert changes.

6. **Memory Usage**: When working with very large GPX files or many files at once, be aware of memory usage.

7. **File Types**: The application preserves the original file type (.gpx) when saving files.

8. **CLI for Automation**: For repetitive tasks, consider using the command-line interface, which can be incorporated into scripts.
