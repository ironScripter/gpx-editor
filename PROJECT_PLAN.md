# GPX Editor Project Plan

This document outlines the plan for implementing the GPX Editor application with the correct order of operations and all required features.

## Correct Order of Operations

1. Select file/files
2. Load attributes for selection
3. Select what operation you would like to perform
4. Program performs operation
5. User selects to save the file/files

## Required Features

- Multiple File Selection
- Display a preview of the selected attribute
  - Show attribute values from all selected files for batch operations via a popup
- All operations are stored in memory until the user chooses to save or not
- When saving multiple files, provide options to prefix or suffix the filename
- Preserve file type in resultant files
- Select destination directory for multiple file operations or standard save window for single files
- Restrict changing file type unless not easily implemented

## Implementation Checklist

### Core Functionality

- [x] Basic GPX file parsing and editing
- [x] Attribute copying and swapping
- [x] Undo/redo functionality
- [x] Automatic backups

### GUI Improvements

- [x] Restructure GUI to follow correct operation order
  - [x] File selection first
  - [x] Attribute loading after file selection
  - [x] Operation selection after attribute loading
  - [x] Save option after operation
- [x] Improve file selection interface
  - [x] Clear indication of selected files
  - [x] Option to remove files from selection
- [x] Add attribute preview functionality
  - [x] Preview panel for single file
  - [x] Popup preview for multiple files
- [x] Enhance save functionality
  - [x] Add prefix/suffix options for batch saves
  - [x] Preserve file type
  - [x] Proper directory selection for batch saves

### Batch Processing Enhancements

- [x] Improve batch file selection
- [x] Add batch attribute preview
- [x] Implement batch operation selection
- [x] Enhance batch save options
  - [x] Prefix/suffix options
  - [x] Directory selection
  - [x] File type preservation

### CLI Improvements

- [x] Update CLI to match new operation flow
- [x] Add batch processing options to CLI
- [x] Implement prefix/suffix options for CLI

### Safety Features

- [x] Filter editable attributes to only allow editing of name, cmt, desc, sym, and type
- [x] Mark non-editable attributes as read-only in the GUI
- [x] Prevent modification of critical attributes like lat/lon in the CLI

### Documentation and Testing

- [x] Update README with new operation flow
- [x] Add examples for all features
- [x] Create sample GPX files for testing
- [x] Create comprehensive user guide
- [ ] Test all features with sample files

## Implementation Plan

### Phase 1: Core Restructuring

1. Restructure the GUI to follow the correct operation order
2. Implement proper file selection and attribute loading
3. Update the operation selection interface
4. Enhance the save functionality

### Phase 2: Feature Enhancements

1. Add attribute preview functionality
2. Implement batch processing improvements
3. Add prefix/suffix options for filenames
4. Ensure file type preservation

### Phase 3: Testing and Documentation

1. Test all features with sample GPX files
2. Update documentation
3. Create user guide
4. Final review and bug fixes

## Task Priorities

1. Restructure GUI for correct operation order
2. Implement attribute preview
3. Enhance batch save options
4. Add prefix/suffix functionality
5. Ensure file type preservation
6. Update CLI to match new flow
7. Update documentation

Let's start with Phase 1 and work through the tasks systematically.
