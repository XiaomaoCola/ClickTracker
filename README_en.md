# ClickTracker

Relative Coordinate Detection Tool for Windows Applications

## Overview

ClickTracker is a Python tool designed to detect mouse click positions within any Windows application window and retrieve relative coordinates and normalized coordinates within that window. While it defaults to targeting "BlueStacks", it can be used with any Windows application.

## Key Features

- **Automatic Window Detection**: Automatically detects any Windows application window containing specified keywords
- **Real-time Coordinate Retrieval**: Retrieves the following coordinates in real-time upon mouse clicks:
  - Screen coordinates (absolute coordinates)
  - Relative coordinates within the window
  - Normalized coordinates (0-1 range)
- **GUI Interface**: Intuitive and user-friendly graphical interface
- **Programmatic API**: Simple API that can be called directly from scripts
- **High DPI Support**: Compatible with high-resolution displays

## Dependencies

```
pyautogui
pywin32
pynput
tkinter (included with Python)
```

## Installation

```bash
pip install pyautogui pywin32 pynput
```

## Usage

### GUI Usage

```bash
python main.py
```

1. Click "检测BlueStacks窗口" button to detect the target window
2. Click "开始监听点击" button to start monitoring
3. Click anywhere within the target window
4. View the displayed relative and normalized coordinates
5. Click "停止监听" button to end monitoring

### Programmatic Usage

```python
from main import SimpleClickDetector

# Initialize detector (defaults to "BlueStacks", can be changed to any keyword)
detector = SimpleClickDetector("Target App Name")

# Convert screen coordinates to relative coordinates
relative_pos, info = detector.screen_to_relative(100, 200)
if relative_pos:
    print(f"Relative coordinates: {relative_pos}")

# Convert relative coordinates to screen coordinates
screen_pos, info = detector.relative_to_screen(50, 75)
if screen_pos:
    print(f"Screen coordinates: {screen_pos}")
```

## Coordinate Types

- **Screen Coordinates**: Absolute coordinates across the entire display
- **Relative Coordinates**: Coordinates within the window's client area (top-left is (0,0))
- **Normalized Coordinates**: Proportional coordinates relative to window size (0.0-1.0 range)

## System Requirements

- Windows 10/11
- Python 3.6+
- Compatible with all Windows applications

## Note

This program can be used on all Windows windows to obtain relative coordinates and standard coordinates.