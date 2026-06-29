---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/02-supervised-vs-unsupervised-machine-learning/06-jupyter-notebooks/","dg-note-properties":{}}
---


### metadata
```run-python {pre}
from pathlib import Path
present_working_directory = Path(@vault_path) / Path(@note_path).parent
current_file_name = @title
video_note = f"{present_working_directory}/{current_file_name}.mp4"

import subprocess
import argparse

def play_video(start, end=None):

    # Construct mpv command
    command = [
        "mpv",
        "--start=" + start,
        "--geometry=1000x500+1920+0",
        video_note
    ]
    
    if end is not None:
	    command.append("--end=" + end)
 
    # Run mpv command
    try:
        subprocess.run(command, stderr=subprocess.DEVNULL, check=True)
    except subprocess.CalledProcessError as e:
        print("Error:", e)
        return
# play_video("00:00:00", "00:00:09")
# play_video("00:00:00")
```

### jupyter notebooks (video can be skipped, notes are enough)

```run-python
play_video("00:00:00")
```
We've seen both supervised and unsupervised learning, along with examples. To really grasp these ideas, why not dive in and try coding them yourself? The go-to tool for this is the **Jupyter Notebook**, which is what most data scientists and machine learning experts use. It's not a simplified version; it's the real deal, the same environment professionals use.

In this class, you'll get to use a **Jupyter Notebook right in your browser** to experiment with these concepts. Don't worry, it's not just for experts. We've made sure it's user-friendly.

You'll come across **optional labs** in this class. They're simple: you just run the code provided, one step at a time. There's no pressure to get it right because there are no grades for these. They're there to help you see how machine learning code works in action. While they're optional, I really think they're worth a look. They're a great way to get a feel for what machine learning code is like.

Next week, we'll introduce practice labs where you'll get to write some code on your own. But for now, just focus on the optional lab and the rest of this week's material.

Let's peek at a notebook example. When you open the first optional lab, feel free to look around. You'll see two types of sections, or "cells": one for **Markdown**, which is just text you can edit, and one for **code**, where the code is already written for you. To run a code cell, press **Shift + Enter**. For a Markdown cell, doing the same will tidy up the text into a nice format.

This lab will show you some basic Python code. When you try it yourself, click on the cells, guess what the code will do, then press Shift + Enter to see if you were right. You can even change the code and see what new things happen.

If you're new to Jupyter Notebooks or Python, this is your chance to become more familiar. I've spent countless hours in Jupyter Notebooks, and I hope you'll enjoy using them as much as I do.

After you've had some fun with the optional lab, I'll see you in the next video. We'll dive into a supervised learning problem and start crafting our first algorithm. I'm sure you'll find it interesting. See you there!


Jupyter Notebooks come with a variety of shortcuts to speed up your workflow. Here are some of the most commonly used ones:

**Command Mode (press `Esc` to enable)**:

- `Enter`: Enter edit mode
- `Shift` + `Enter`: Run the cell and select the cell below
- `Ctrl` + `Enter`: Run the cell
- `Alt` + `Enter`: Run the cell and insert a new cell below
- `Y`: Change the cell to a code cell
- `M`: Change the cell to a markdown cell
- `Up` or `K`: Select the cell above
- `Down` or `J`: Select the cell below
- `A`: Insert a new cell above
- `B`: Insert a new cell below
- `D`, `D` (press the key twice): Delete the selected cell
- `Z`: Undo the last cell operation
- `S`: Save and checkpoint
- `L`: Toggle line numbers
- `Shift` + `M`: Merge selected cells, or current cell with cell below if only one cell is selected
- `Shift` + `L` (L on some layouts): Toggle line numbers for all cells

**Edit Mode (press `Enter` to enable)**:

- `Esc`: Enter command mode
- `Tab`: Code completion or indent
- `Shift` + `Tab`: Tooltip
- `Ctrl` + `]`: Indent
- `Ctrl` + `[`: Dedent
- `Ctrl` + `A`: Select all
- `Ctrl` + `Z`: Undo
- `Ctrl` + `Shift` + `Z` or `Ctrl` + `Y`: Redo
- `Ctrl` + `Home`: Go to cell start
- `Ctrl` + `End`: Go to cell end
- `Ctrl` + `Left`: Go one word left
- `Ctrl` + `Right`: Go one word right
- `Ctrl` + `Backspace`: Delete word before
- `Ctrl` + `Delete`: Delete word after
- `Ctrl` + `M`: Enter command mode
- `Shift` + `Enter`: Run cell, select below
- `Ctrl` + `Shift` + `-`: Split the cell at cursor

**Other Shortcuts**:

- `I`, `I`: Interrupt the kernel
- `0`, `0`: Restart the kernel (with dialog)
- `Shift` + `Space`: Scroll notebook up
- `Space`: Scroll notebook down

**Accessing the Command Palette**:

- `Ctrl` + `Shift` + `P`: Open the command palette to search commands

Remember, these shortcuts can differ slightly depending on the operating system and the browser you are using. Also, you can always find the list of all shortcuts in the Help menu of Jupyter Notebook, and you can even customize your own shortcuts.