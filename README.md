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

```
Autoloader-BBC/
│
├── src/          # Original ADE source files
├── rom/          # Compiled ROM images
├── docs/         # Supporting documentation
│   ├── FEATURES.md
│   ├── COMMANDS.md
│   ├── BUILD.md
│   └── HISTORY.md
├── screenshots/  # Program snapshots
└── README.md     # This file
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

## License

This repository does not include a license by default. Use at your own discretion.