# Change Log

All notable changes to the "mega-increment" extension will be documented in this file.  
File is structured by following recommendations from [Keep a Changelog](http://keepachangelog.com/).  
Extension versions follow [Semantic Versioning](https://semver.org/).



## [1.2.5] - 2024-03-27

### Added
- Readme.md update.



## [1.2.4] - 2024-03-19

### Fixed
- API call responses.
- Code optimisations, clean-up, styling.



## [1.2.3] - 2024-02-17

### Fixed
- Workaround for porblem with failed api calls through Vercel.



## [1.2.2] - 2024-02-15

### Added
- Verification of option sets through new API.

### Fixed
- Automatic textarea width.
- GUI structure.
- Readme corrections.
- API 404 pages.



## [1.2.1] - 2024-02-12

### Added
- Editor: Moving cursor to different line continues increments at new location.

### Fixed
- Misplaced increments when cursor is at EOL.
- UI messages and info for editor.
- Readme typos and corrections.



## [1.2.0] - 2024-02-10

### Added
- Along the existing hh:mm:ss new ISO time formats: hh:mm, mm:ss.
- Along the existing YYYY-MM-DD New ISO date formats: YYYY-MM, MM-DD.
- Leading zeros support for integer and floating point numbers.
- New GUI button behavior for timeISO and dateISO.
- Readme updated.
- Public API updated with Terms of Use and Privacy Policy.

### Fixed
- Configuration vscode engine for compatibility with previous versions of VSCode.
- Script files for public repository.
- Extension settings for packaging.
- HTML infrastructure for GUI.
- Text instead of HTML output to selections text section.
- Hidden bug for time format increments.

## Deprecated
- In public MACf types timeISO and dateISO are replaced with YYYY-MM-DD, YYYY-MM, MM-DD, hh:mm:ss, hh:mm, mm:ss.
- Public API Docs updated.



## [1.1.0] - 2024-02-06

### Added
- Right click for Add selection and Advanced GUI.
- Click on Status bar for Increment and Clear selections.
- Readme additions and fixes.

### Fixed
- No need to restart VSCode/extension for some settings to take effect.
- YouTube videos changed from mp4 to mpg for slightly better quality.



## [1.0.9] - 2024-02-05

### Added
- New logo.
- New repo configuration.
- Simplified notifications and added option for disabling all notifications except for overlapping selection(s).


## [1.0.8] - 2024-02-03

- Fix for permutated shortcuts for Mac.
- Typos in Docs.


## [1.0.7] - 2024-02-02

- About page @ vezbamo.
- Fix for html entities in line text.
- Linkedin update.
- Details at config files.


## [1.0.6] - 2024-02-02

- New Readme useer suggestions and updates.


## [1.0.5] - 2024-02-02

- Readme updates.


## [1.0.4] - 2024-02-02

- Extension name at marketplace fix.


## [1.0.3] - 2024-02-02

- Public API Docs and home page changes.



## [1.0.2] - 2024-02-01

- Auto API link generator fixed to point @ vezbamo API end point.


## [1.0.1] - 2024-02-01

- Typos...


## [1.0.0] - 2024-02-01

- Extension published on Visual Studio Code Marketplace and to all.


## [0.9.3] - 2024-02-01

### Fixed
- GUI for white background and smaller displays.
- GUI for fresh instalations.

### Added
- Readme links, contents and fixes.


## [0.9.2] - 2024-01-31

- Bundling and packing.

### Fixed
- Same colors in GUI for all selections except enum and hex.


## [0.9.1] - 2024-01-31

### Deprecated
- Extension not enabled in Windows 7 despite lowering VSCode engine and @types/vscode to 1.62.0.

### Added
- Windows 10 quirks documented in Read.me.
- Empty lines in Change log for compatibility with older markdown parsers.
- New icon.
- Videos on YouTube.

## [0.9.0] - 2024-01-31

### Added
- Local pack.
- GitHub repo in package.json for media.
- Icon link.


## [0.8.1] - 2024-01-31

### Added
- GitHub issue tracking and repo details.

### Fixed
- Readme incompatibilities for markdown at VSCode and GitHub.


## [0.8.0] - 2024-01-31

### Added
- Git choose dirs and files, new repository, new repo at GitHub.


## [0.7.4] - 2024-01-31

### Fixed
- Button for curl API export to return to normal after second click.

### Added
- Copyrights.


## [0.7.3] - 2024-01-30

### Fixed
- API test and calculations moved to same loop for siplicity and to provide more information on errors to user.
- Removed API error on missing stepping for crypto and random.

### Added
- GUI increment remains saved in ext until GUI tab is closed or nothing changed.
- New editor and GUI animated gif and mp4 video for Linkedin etc.


## [0.7.2] - 2024-01-30

### Fixed
- GUI image in Readme.md for new arrangement of buttons.
- Auto cols for lineText and result.
- Problem with curl and http API cals and JSON parsing.


## [0.7.1] - 2024-01-29

- Keybindings in package.json.
- More info added to info window which user get by clicking on status bar.
- Disabled auto cols and font-size formatting for lineText and result.
- Restructured buttons in GUI for get line text and exporting results.
- Recreated animated gif for editor.
- Found problem with curl and http API cals and JSON parsing.


## [0.6.10] - 2024-01-28

- Printscreens in Readme.md and fixing additional text and UI/UX stuff.


## [0.6.9] - 2024-01-27

- Spelling check and text corrections for change log, API docs, Readme.md.


## [0.6.8] - 2024-01-26

### Fixed 
- GUI: to show enum key alongside enum type.
- GUI: floating point stepping truncated to integer at next render of selections.

### Added
- If stepping for enum is floating point enumVariant for selection is changed to 'continuous'.
- More on readme.md.


## [0.6.7] - 2024-01-25

### Deprecated
- In GUI Alt+8 is not shortcut for retrieving lineText but for focus on lineText textarea.

### Added
- Fractional stepping for integers, dateISO, timeISO and enums.
- Enums in Readme.md.


## [0.6.6] - 2024-01-24

### Fixed
- Updated and cleared todos.
- Fixed bug in GUI after clear selections.
- Finished textual work on editor part for Readme.md except for enums.


## [0.6.5] - 2024-01-23

- Investigated Node DeprecationWarning: for Buffer() and it is probably due to update of some dependency component because extension doesn't use it. Some testing code in vezbamo uses Buffer but new version which is not deprecated. It doesn't affect extension so will be ignored.
- Investigated folder structure and restructured itd. with new folder, workspace etc.
- Found bug in GUI: no new incrementations in result after clear selections although new selections are visible.


## [0.6.4] - 2024-01-23

### Fixed
- Changed arrangement of options in editor to: number, enum, date, time, simple, hex, binary, crypto, random.
- Some errors and typos in this file.

### Added
- All types for JSON data section keys in API docs.
- Some new test for API request data.


## [0.6.3] - 2024-01-22

### Fixed
- Linux/Mac/Win shortcuts.
- Code translation and cleaning.

### Added
- API tests, protection, quirk response for https requests with risky html tags.


## [0.6.2] - 2024-01-21

### Fixed
- Enum increment with positive and negative stepping.

### Added
- Two variants for enums: ranged and continuous.
- ISO date, ISO time, hex, binary, random, crypto for MACf docs.

## [0.6.1] - 2024-01-19
- Deactivate method cleared.
- Extension settings in GUI.
- Restructure and simplification for core functions in extension and @ vezbamo.


## [0.6.0] - 2024-01-18

### Added
- Core functions integrated via api-like interface for editor and GUI.
- Feature to produce curl API call for Linux in GUI.
- Public API with core functions is working @ vezbamo.vercell.app/api/mi/v1
- MACf (Mega-increment API Core functions) docs contain basic working examples for public API.

### Fixed
- Structure and contents for todo.md.


## [0.5.2] - 2024-01-17

- Restructured GUI app in mini front-end framework and simplified extension structure.
- Preparations for GitHub repository.

### Added
- Copy GUI result to clipboard.
- Convert GUI result to JSON.

### Fixed
- Send GUI result to editor.
- Multi line text for GUI.
- Textarea size for lineText and result depending on text length and line numbers.


## [0.5.1] - 2024-01-15

### Added
- Docs, web GUI, change log & readme integrated @ vezbamo, changes pushed, repo set to private.


## [0.5.0] - 2024-01-11

### Added
- First implementations of same core functions in editor and GUI.
- As crypto.

### Fixed
- Unnecessary stepping for random and crypto.


## [0.4.3] - 2024-01-08

### Added
- In editor:
    + As enum.
    + As ISO date.
    + As ISO time.
    + As hex.
    + As binary.
    + As random.

### Fixed
- Select mode function to accommodate all present modes besides simple and number.


## [0.4.2] - 2024-01-03

### Added
- Public API endpoint @ vezbamo.

### Fixed
- Bug with processed selection strings in increments and cursor position calculation.


## [0.4.1] - 2024-01-02

- Separated change log, notes and todos.

### Added
- In GUI:
    + As ISO date.
    + As ISO time.
    + As hex.
    + As binary.
    + As random.
- Readme features and parts of manual and gifs.


## [0.3.2] - 2023-12-30

### Added
- Accesskeys for GUI: Alt+0 del selections, Alt+8 focus on line text editor.
- Refactor entire segmentation system which enabled enums to be implemented in editor, and code to be shared across editor, GUI and future API.
- Processing of selected and UI improvements.
- Line editing in GUI during selection adding and removing.
- Enum insert and selection improved with separate buttons for inserting enum and As enum.
- Recognizing enums in the moment of selecting part of text.
- Editing of lineText when selection is in homogenous strings.

### Fixed
- Bug with negative enum stepping.
- Bug for retained line text selection and selected enum corruption.
- Bug with failing insert after insert as enum, edit.        


## [0.2.4] - 2023-12-21

### Fixed
- After clear result app stuck and even if it's rendering list of selections still doesn't render result. Fixed with textContent instead of value.

### Added
- enums:
    + custom enum insert i.e. two in row, not one in between each character
    + negative i.e. reverse stepping for enums
    + independent counters for multiple enums
    + support for up to 3 enums in one unselected region
    + reformated enums sections in settings
- GUI:
    + enums before selections
    + different colors in selections for Basic, JS, C
    + checkbox for deleting selections
    + separators for segments, separator for different enums
    + redesign of enums and selections lists


## [0.2.2] - 2023-12-18

### Fixed
- After clear result app stuck and even if it's rendering list of selections still doesn't render result. Fixed with textContent instead of value.

### Added
- Automatic adjustment of results height according to number of repeats for increment.

### Deprecated
- Integer and decimal separation, now they are merged in editor and GUI.
- More UI/UX improvements.


## [0.2.1] - 2023-12-16

- Compacted UI and styling.
- Changed enum display.
- Started work on README.md contents.
- Work on draft for expansions.

### Added
- Stepping for GUI.
- Keyboard text select.


## [0.1.9] - 2023-12-15

### Added
- Same functionality for GUI as in file editor.
- Decimal increment.
- UI/UX improvements for editor and GUI.
- Low level routing on local Node server for easier testing for preview and ext UI.

### Fixed
- Several small bugs.
- Number not recognized in editor when number ends with zero.
- Overloading of template string in ext with adv html js code alleviated with imported js code in html and changes on local server to adapt adv html page accordingly.


## [0.1.4] - 2023-12-09

- Further outlining of next actions.
- Reorganized main extension code.

### Added
- Markdown change log.
- TO-DOs moved to change log Unreleased section.
- Separate TextEditorCommand for global editor in order to make standard and simpler import of text line to GUI.
- Buttons for space and enums.
- Implemented dedicated variable which places complex adv logic to GUI instead to ext.
- Local server upgraded to update main extension code with GUI adv html file content in place of existing template literal html string.


## [0.1.2] - 2023-12-08

- Fine tuned all about settings.

### Added
- Interaction of settings with extension
- GUI:
    + Local image display
    + Local custom Node server for interactive html edit and render.
    + Messaging between extension and GUI for advanced increment.
    + Formating GUI for basic functionality.

### Security
- Restricted image use only from media folder.
    

## [0.1.1] - 2023-12-07

- Outlining bugs and next actions.

### Fixed
- Bugs:
    + for one more line jump
    + same line increment
    + last text doubling on copy line.

### Added
- Feature to just copy current line if there are no selections for in/decrement.
- First entries in extension settings.
- HTML change log.


## [0.1.0] - 2023-12-06

### Fixed
- Manage empty selection. 
- Manage overlapping selections and at same time adding delete for unwanted selection.
- Several bugs.

### Added
- Stepping for increment/decrement via input box.
- Status bar elements.
- Basic GUI for advanced increment/decrement.
- Number mode via quick pick.

### Removed
- Removal of separate inc/dec commands and implementing as one command.

### Deprecated
- Commands reassigned for `crtl+shift+`:
    + `8`: in/decrement
    + `insert`: copy
    + `delete`: clear
    + `9`: advanced increment GUI


## [0.0.2] - 2023-12-05

### Added
- Commands for increment, decrement, copy, clear, adv at: crtl+shift+ 3, 4, insert, 8, 9 respectively.


## [0.0.1] - 2023-12-04

- Installing appropriate system software.
- Setting up extension.
- Basic functionality for interacting with file editor.


## [0.0.0] - 2023-12-03

- In the previous period during some programming tasks I needed functionality for parallel independent incrementations and decrementations in complex strings. So I searched extensions for VSCode but didn't find what I needed. Then I came up with the idea of making an extension with such functionalities and made first draft.

## Licence
Copyright (C) Vladan Anđelković. All rights reserved.