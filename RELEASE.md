# GPX Editor Release Notes

## v1.0.0-beta (May 2, 2025)

This is the initial beta release of the GPX Editor tool, a Python utility for editing and manipulating GPX files.

### Features

- **Core GPX Editing**
  - Copy attributes between waypoints
  - Swap attribute values
  - Process individual or all waypoints in a file
  - Automatic backup creation before modifications

- **File Renaming**
  - Rename GPX files based on directory structure
  - Apply abbreviations to directory names (2-3 letters in length)
  - Reverse directory order in filenames (deepest directory first)
  - Use hyphens as separators (e.g., "D3-D2-D1.gpx")
  - Exclude original filename from the new name

- **User Interfaces**
  - Command-line interface with argparse
  - Full-featured GUI with Tkinter
  - Batch processing capabilities

- **Development Improvements**
  - Poetry-based dependency management
  - Proper package structure for PyPI distribution
  - GitHub Actions for automated publishing

### Installation

```bash
# Install from PyPI
pip install gpx-editor

# Or using Poetry
poetry add gpx-editor
```

### Usage Examples

**Command Line Interface:**
```bash
# Basic attribute operations
gpx-editor --input input.gpx --output output.gpx --copy description name
gpx-editor --input input.gpx --output output.gpx --swap description name --all

# File renaming based on directory structure
gpx-editor --input path/to/your/gpx/file.gpx --rename
```

**GUI Interface:**
```bash
# Launch the graphical interface
gpx-editor-gui
```

### Known Issues

- Large GPX files may experience performance issues in the GUI
- Some complex nested attributes may not be properly displayed in the preview

### Upcoming Features

- Support for track and route elements in addition to waypoints
- Batch processing improvements
- Advanced filtering capabilities
- Command-line completion

### Breaking Changes

- None (initial release)

### Dependencies

- Python 3.7+
- xmltodict

### Contributors

- James Arnett
