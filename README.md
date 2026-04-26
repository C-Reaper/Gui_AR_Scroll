## Overview
The project appears to be a C program that integrates Optical Flow and Augmented Reality (AR). It seems to display an AR overlay on the user's camera feed, highlighting regions of motion using Optical Flow. The application also includes a scrolling mechanism controlled by the user.

## Features
- Real-time optical flow calculation
- AR overlay displaying motion detection
- Scrolling functionality

## Project Structure
```
Gui_AR_OF_Scroll/
├── build/              # .exe files produced by Main.c
├── src/                # source code
│   ├── Main.c          # Entry point
│   └── *.h             # header-based C-files, without *.c files that implement it
├── Makefile.linux      # Linux Build configuration
├── Makefile.windows    # Windows Build configuration
├── Makefile.wine       # Wine Build configuration
└── README.md           # This file
```

### Prerequisites
- C/C++ Compiler and Debugger (GCC, Clang)
- Make utility
- Standard development tools
- Libraries needed in specific projects:
  - **Linux**: X11 for GUI, libpng/libjpeg for image handling
  - **Windows**: User32/GDI32/Winmm for GUI and multimedia functions
  - **WebAssembly**: Emscripten for compiling to WebAssembly

## Build & Run
### Linux
```sh
cd Gui_AR_OF_Scroll/
make -f Makefile.linux all
```

To execute:
```sh
./build/Main
```

### Windows
```sh
cd Gui_AR_OF_Scroll/
make -f Makefile.windows all
```

To execute:
```sh
./build/Main.exe
```

### Wine (Cross-compiling for Windows on Linux)
```sh
cd Gui_AR_OF_Scroll/
make -f Makefile.wine all
```

To debug:
```sh
WINEPREFIX=~/wine64 WINEARCH=win64 winedbg build/Main.exe
```

To execute:
```sh
WINEPREFIX=~/wine64 WINEARCH=win64 wine build/Main.exe
```

### WebAssembly (Emscripten)
```sh
cd Gui_AR_OF_Scroll/
make -f Makefile.web all
```

To run in a web browser:
```sh
emrun --no_browser --port 8080 build/index.html
```