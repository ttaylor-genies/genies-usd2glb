# Building usd2glb on Windows for Debugging

## Prerequisites

1. **CMake**: Download from https://cmake.org/download/ (add to PATH during install)
2. **Visual Studio 2019/2022**: Community edition with C++ desktop development workload
3. **Git**: Already installed

## Build Steps

### 1. Open PowerShell in project directory:
```powershell
cd C:\dev\genies-usd2glb
```

### 2. Configure CMake (Debug build):
```powershell
cmake -B build -DCMAKE_BUILD_TYPE=Debug
```

### 3. Build:
```powershell
cmake --build build --config Debug
```

The executable will be at: `build/Debug/usd2glb.exe`

## Debugging in Cursor

1. Open `C:\dev\genies-usd2glb` in Cursor
2. Install C/C++ extension if prompted
3. Update `.vscode/launch.json` with your USD file path
4. Set breakpoints (try line 163 in main.cpp: `stage.root_prims()[0]`)
5. Press F5 to start debugging

## Quick Test

```powershell
.\build\Debug\usd2glb.exe path\to\avatar.usd output.glb
```

## Troubleshooting

**CMake not found**: Add CMake bin directory to PATH (usually `C:\Program Files\CMake\bin`)

**No compiler found**: Open "x64 Native Tools Command Prompt for VS 2022" and run commands there

**Submodules missing**:
```powershell
git submodule update --init --recursive
```
