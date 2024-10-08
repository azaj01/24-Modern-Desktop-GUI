[![GitHub](https://img.shields.io/github/license/KhamisiKibet/24-Modern-Desktop-GUI?logo=Github)](https://github.com/KhamisiKibet/24-Modern-Desktop-GUI/blob/master/LICENSE) [![GitHub top language](https://img.shields.io/github/languages/top/KhamisiKibet/24-Modern-Desktop-GUI?logo=github)](https://github.com/KhamisiKibet/24-Modern-Desktop-GUI) [![GitHub code size in bytes](https://img.shields.io/github/languages/code-size/KhamisiKibet/24-Modern-Desktop-GUI?logo=github)](https://github.com/KhamisiKibet/24-Modern-Desktop-GUI) [![GitHub issues](https://img.shields.io/github/issues/KhamisiKibet/24-Modern-Desktop-GUI?logo=github)](https://github.com/KhamisiKibet/24-Modern-Desktop-GUI/issues)
![GitHub repo size](https://img.shields.io/github/repo-size/KhamisiKibet/24-Modern-Desktop-GUI)
![GitHub stars](https://img.shields.io/github/stars/KhamisiKibet/24-Modern-Desktop-GUI?style=social)
![GitHub forks](https://img.shields.io/github/forks/KhamisiKibet/24-Modern-Desktop-GUI?style=social)
[![Twitter Follow](https://img.shields.io/twitter/follow/KhamisiKibet?style=social)](https://twitter.com/intent/follow?screen_name=KhamisiKibet)
[![YouTube Video Views](https://img.shields.io/youtube/views/JK-B-CT34EU?style=social)](https://youtu.be/JK-B-CT34EU)

![24 modern desktop gui GIF](https://github.com/KhamisiKibet/Docs-QT-PyQt-PySide-Custom-Widgets/raw/main/images/24-modern-ui.gif)

[Check out the Exe app above](https://www.dropbox.com/scl/fi/i0s1imjm5a1rvs00xdrra/24-Modern-GUI-exe.zip?rlkey=aka3fjexl0krtjq231chdnd6y&st=1fiksoky&dl=0)

# Creating a PySide6 Project with Custom Widgets and PyInstaller

[Watch youtube tutorial](https://youtu.be/JK-B-CT34EU?si=l6wbCzPnmxCdLkir)

## 1. Install Python
First, ensure that you have Python installed on your system. You can download Python from [python.org](https://www.python.org/downloads/).

## 2. Install the Custom Widgets Module
Next, install the custom widgets module from GitHub using pip:
```bash
pip install QT-PyQt-PySide-Custom-Widgets
```

Remember to also install PySide6, PyQt6,PySide2 or PyQt5(Recommended: PySide6 or PyQt6)
```bash
pip install PySide6
```

## 3. Create a New Project
Create a new PySide6 project using the custom widgets project maker command:
```bash
Custom_Widgets --create-project
```

## 4. Open the Project Folder
Navigate to the project folder that was created.

## 5. Edit the UI in Qt Designer
Inside the project folder, open the `ui` folder and start editing the UI using Qt Designer.

## 6. Monitor UI Changes
While editing the UI, open a terminal inside the project folder and run the following command to monitor UI files for changes:
```bash
Custom_Widgets --monitor-ui ui
```
This will automatically convert UI files to Python and generate necessary files for the custom widgets module.

## 7. Preview the UI
After finishing the UI design, preview it to ensure everything looks as expected.

## 8. Add GUI Functions and Classes
Now, add other GUI functions and classes inside the Python files (e.g., `main.py`).

## 9. Customize and Style the GUI
Customize and style your GUI using the custom widgets module. This module will read the JSON files and QSS stylesheet files inside the project folder.

## 10. Convert the GUI App to an Executable
Finally, convert your GUI application to an executable using PyInstaller. First, install PyInstaller:
```bash
pip install pyinstaller
```

### Generate the Spec File
Next, generate the spec file for your project:
```bash
pyi-makespec --onefile --windowed main.py
```

### Edit the Spec File
Open the generated `.spec` file and edit it as shown below. Replace names and paths as necessary:

```python
# -*- mode: python ; coding: utf-8 -*-

block_cipher = None

a = Analysis(
    ['main.py'],
    pathex=[],  # Add paths if needed
    binaries=[],
    datas=[],  # Add data files if needed
    hiddenimports=['PySide6'],  
    hookspath=[],
    hooksconfig={},
    runtime_hooks=[],
    excludes=['PyQt5', 'PySide2', 'PyQt6'],  
    noarchive=False,
)

pyz = PYZ(a.pure)

exe = EXE(
    pyz,
    a.scripts,
    [],
    exclude_binaries=True,
    name='YourAppName',  # Set the name of your executable
    debug=False,
    bootloader_ignore_signals=False,
    strip=False,
    upx=True,
    console=False,  # Set console to False
    disable_windowed_traceback=False,
    argv_emulation=False,
    target_arch=None,
    codesign_identity=None,
    entitlements_file=None,
    icon='path/to/your/icon.ico'  # Replace 'path/to/your/icon.ico' with the path to your icon file
)

coll = COLLECT(
    exe,
    a.binaries,
    a.datas,
    strip=False,
    upx=True,
    upx_exclude=[],
    name='main',
)
```
### Build the Executable
Finally, build the executable using the edited spec file:
```bash 
pyinstaller your_spec_file.spec
```

### Locate the Executable
After the build process is complete, the executable will be located in the dist folder inside your project directory. The path will be similar to:
```bash
your_project_folder/dist/YourAppName.exe
```

*Note*: Remember to copy other required static data files to your exe folder.

## ☕️ Support My Work

Hey there! If you enjoy my projects and find them helpful, consider buying me a coffee. Your support helps me keep going and create more awesome content! 😊

[![Buy Me a Coffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-FFDD00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://www.patreon.com/spinntv)

