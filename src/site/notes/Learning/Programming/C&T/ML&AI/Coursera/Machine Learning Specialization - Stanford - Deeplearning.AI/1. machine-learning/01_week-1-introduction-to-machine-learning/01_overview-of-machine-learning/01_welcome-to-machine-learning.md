---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/01-overview-of-machine-learning/01-welcome-to-machine-learning/","dg-note-properties":{}}
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

### What is machine learning?  (can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```
**<span style="color:#000000">It is a science enabling computers to learn without explicitly being programmed.</span>**
Examples :
- When you search in google "How to make a sushi" you get the answers because the machine learning software has learnt how to rank web pages
- When you go to Instagram, snap chat and you want to tag your friends the ML does it for you
- If you just watched a star wars movie and you get suggestions for similar movies that you can watch . This is machine learning
- When you ask google to show Indian restaurants near you
- When you get fake email like "Congratulation you have won 1 million dollars" and email service flags that as a span . This is also machine learning
Machine learning is also used in
- Optimizing wind turbine power generation
- Health care to make accurate diagnosis
- computer vision to detect faults in anything coming from the assembly line in factories.
