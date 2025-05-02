# GPX Editor Release Notes

## v1.0.1-beta (May 2, 2025)

This release includes several improvements and enhancements to the GPX Editor tool based on user feedback and requirements.

### Improvements

- **CLI Enhancements**
  - Switched from Click to argparse for command-line argument parsing
  - Added support for batch processing multiple files
  - Improved error handling and logging
  - Added prefix/suffix options for batch file saving

- **File Renaming Enhancements**
  - Improved directory-based file renaming
  - Abbreviations are now consistently 2-3 letters in length
  - Excluded original filename from the new name
  - Used hyphens without spaces as separators (e.g., "D3-D2-D1.gpx")
  - Reversed the order of directories (deepest directory first)
  - Example: For a file path D1/D2/D3/F.gpx, the new filename is now "D3-D2-D1.gpx"

- **Attribute Operations**
  - Added attribute preview functionality
  - Improved batch attribute operations
  - Enhanced safety features to prevent modifying critical attributes

- **GUI Improvements**
  - Restructured GUI to follow correct operation order
  - Improved file selection interface
  - Added clear indication of selected files
  - Added option to remove files from selection
  - Enhanced save functionality with prefix/suffix options

- **Dependency Management**
  - Converted project to use Poetry for dependency management
  - Added poetry.lock file for reproducible builds
  - Maintained compatibility with pip via requirements.txt

- **Documentation**
  - Added comprehensive USER_GUIDE.md
  - Updated README.md with new features and usage examples
  - Added PROJECT_PLAN.md for development tracking

- **Sample Files**
  - Added sample GPX files for testing
  - Included nested directory structure for testing file renaming

### Bug Fixes

- Fixed issue with attribute swapping in batch mode
- Resolved file path handling on different operating systems
- Fixed memory leaks when processing large GPX files
- Improved error handling for malformed GPX files

### Known Issues

- Large GPX files may experience performance issues in the GUI
- Some complex nested attributes may not be properly displayed in the preview

### Upcoming Features

- Support for track and route elements in addition to waypoints
- Advanced filtering capabilities
- Command-line completion

### Dependencies

- Python 3.8+
- xmltodict 0.13.0+
- Poetry for dependency management

### Contributors

- James Arnett
