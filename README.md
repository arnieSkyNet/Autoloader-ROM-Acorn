# **README.md**

```
# Autoloader for the Acorn BBC Micro

**Autoloader** is a BBC Micro ROM originally written in 6502 assembly language using the ADE ROM assembler.  
Its primary purpose is to automatically load the VIEW word processor when VIEW-format files are selected, add an extended menu inside VIEW, and detect the filesystem type (DFS, ADFS, or ANFS). Optional Winchester-style chimes can also be played every 15 minutes.

## Features
- Auto-detect DFS/ADFS/ANFS
- Automatically launches VIEW for VIEW-format files
- Extends VIEW with additional menu options
- Optional Winchester-style chimes
- Preserves ADE-specific assembly syntax in source

## Installation
- Manual ROM load is supported as usual on the BBC Micro.
- If the ROM is located in `$.Library._HH`, a utility (also in Library) can autoload it on boot.

## Usage
- Autoloader automatically launches VIEW when a VIEW-format file is selected.
- Once in VIEW, pressing `Esc` will reveal a menu with options to save or exit back to the file explorer.
- Use the `*H` command in VIEW to see all available commands and features.

## Repository Structure
```
Autoloader-BBC/
│
├── src/        # Original ADE source files
├── rom/        # Compiled ROM images
├── docs/       # Supporting documentation
│   ├── FEATURES.md
│   ├── COMMANDS.md
│   ├── BUILD.md
│   └── HISTORY.md
└── README.md   # This file
```

## License
This repository does not include a license by default. Use at your own discretion.
```

---

# **docs/FEATURES.md**

```
# Autoloader Features

- **Auto-detect file systems:** DFS, ADFS, ANFS
- **Automatic VIEW launch:** Opens VIEW word processor for VIEW-format files
- **VIEW menu extension:** Additional options accessible after exiting editing
- **Winchester-style chimes:** Optional, every 15 minutes
- **Preserved ADE source:** All code retains original ADE assembler directives
- **Autoload support:** Can automatically load ROM if placed in `$.Library._HH`
```

---

# **docs/COMMANDS.md**

```
# Autoloader Commands

- Press `Esc` in VIEW to access the Autoloader menu
- Menu options include:
  - Save
  - Exit back to file explorer
- Press `*H` at any time to view all available commands and features
```

---

# **docs/BUILD.md**

```
# Building Autoloader

## Original ADE Source
- Written using ADE ROM assembler on the BBC Micro
- Source uses ADE-specific syntax and directives
- Assemble using ADE to produce a `.ROM` image

## Modern Considerations
- ADE source can be preserved in `src/`
- ROM images can be placed in `rom/`
- No modifications are required to run on original BBC Micro hardware
```

---

# **docs/HISTORY.md**

```
# Autoloader History

- **Original Development:** Written in the 1980s–1990s on a BBC Micro using ADE assembler
- **Purpose:** Automate the loading of VIEW word processor files and extend its menu system
- **Filesystem Support:** Automatically detects DFS, ADFS, or ANFS
- **Additional Features:** Optional Winchester-style chimes every 15 minutes; autoload support from `$.Library._HH`
- **Preservation:** Source retains ADE-specific syntax for historical authenticity
```
