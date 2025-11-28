# Autoloader for the Acorn BBC Micro

**Autoloader** is a BBC Micro ROM originally written in 6502 assembly using the ADE ROM assembler.  
Its primary purpose is to automatically launch the VIEW word processor when VIEW-format files are selected, extend the VIEW menu, and detect the filesystem type (DFS, ADFS, or ANFS). Optional Winchester-style chimes can also be played every 15 minutes.

---

## Features

- Auto-detect file systems: DFS, ADFS, ANFS  
- Automatically launch VIEW for VIEW-format files  
- Extended VIEW menu accessible after exiting editing  
- Optional Winchester-style chimes  
- ADE source preserved for historical authenticity  
- Autoload support from `$.Library._HH`  

---

## Repository Structure

The project is organised as follows:

```
Autoloader-BBC/
├── src/               Source code (.ADE, include files, workspace files)
│   ├── main/          Main program and INCLUDE tree
│   ├── include/       Subroutine files included by main
│   ├── ade/           ADE support files (if applicable)
│   └── library/       Any ADE or BBC BASIC library files needed for build
├── rom/               Compiled ROM images (built output)
├── docs/              Additional documentation
│   ├── FEATURES.md
│   ├── BUILD.md
│   ├── COMMANDS.md
│   └── HISTORY.md
├── screenshots/       Images showing ROM behaviour
└── README.md          Main project overview (this file)
```

---

## Screenshots

Place your program snapshots in the `screenshots/` folder. Example:

```markdown
![VIEW menu screenshot](screenshots/view_menu.png)
![Filesystem detection screenshot](screenshots/filesystem_detect.png)
```

---

## Built ROM

The compiled ROM image(s) can be found in the `rom/` folder. Example:

```
rom/autoloader.rom
```

---

## Building the ROM on a BBC Micro (Using ADE)

This project can be built on a real BBC Micro or emulator using ADE (Advanced Disk Editor).

### Requirements
- ADE assembler and emulator ROMs:
  - `ADEasm`
  - `ADEmmu`
- The ADE Library (usually found in: `$.Library.BasicProg.AT_Sources.Library`)
- All source files present in the `src/` directory

### Step 1 — Load ADE support modules
Load the ADE assembler and emulator modules into sideways RAM:

*RLOAD %.ROMS.ARCH*.ADEasm 4
*RLOAD %.ROMS.ARCH*.ADEmmu 5
*LIB :*0.$.Library.BasicProg.AT_Sources.Library

### Step 2 — Change to the source directory
Navigate to the folder containing the AUTOLAUNCH wrapper and source:

*DIR <your-source-directory>

### Step 3 — Assemble the ROM
Run ADE with the AUTOLAUNCH wrapper file:

*ASM AUTOLAUNCH

### Step 4 — Output ROM
ADE will assemble starting at &8000.
If AUTOLAUNCH contains a SAVE statement, the ROM will be written automatically.

Otherwise, save manually:

*SAVE AUTOLOADER &8000 &BFFF

This creates a ROM image suitable for a sideways ROM socket or emulator.

---

## Building the ROM on Windows/Linux/Mac (Using BeebAsm)

This project can also be assembled using the modern BeebAsm assembler.

### Requirements
Install BeebAsm:

Windows:
  Download binary from: https://github.com/stardot/beebasm/releases

Linux / macOS:
  git clone https://github.com/stardot/beebasm
  make

### Step 1 — Go to the project folder

cd Autoloader-BBC

### Step 2 — Assemble the ROM

beebasm -i src/main/autoloader_main.asm -o rom/Autoloader.rom -v

(You can replace the input path with your actual main source file.)

### Step 3 — Load the ROM in an emulator

BeebEm:
  File → Load ROM → choose rom/Autoloader.rom → Slot 4

B-Em:
  Hardware → Load ROM → select slot → choose rom/Autoloader.rom

### Notes
- INCLUDE paths may need adjusting for BeebAsm (uses `.include "file"` syntax)
- Workspace definitions may need slight conversion
- All logic, routines, and labels will assemble identically once syntax updates are made

---


## License

This repository does not include a license by default. Use at your own discretion.