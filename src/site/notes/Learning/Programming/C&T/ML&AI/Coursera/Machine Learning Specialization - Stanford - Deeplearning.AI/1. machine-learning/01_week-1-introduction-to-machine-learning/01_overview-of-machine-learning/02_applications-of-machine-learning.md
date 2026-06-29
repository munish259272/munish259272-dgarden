---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/01-overview-of-machine-learning/02-applications-of-machine-learning/","dg-note-properties":{}}
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

### applications of machine learning  (can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

In this course, you'll learn about machine learning, a field that focuses on creating intelligent systems. We'll cover important algorithms used in big tech companies, and you'll get hands-on experience implementing them. The goal is to equip you with practical tips for making these algorithms perform well.

Why is machine learning so widely used today? It originated as a part of artificial intelligence (AI) with the aim of building intelligent machines. **<span style="font-weight:bold; color:#000000">Traditional programming could handle simple tasks, but more complex ones like web search, speech recognition, and self-driving cars required machines to learn by themselves.</span>**

Throughout my career, I've worked on various AI projects, from speech recognition at Google to AI applications in augmented reality and self-driving cars. Today, machine learning is applied across industries like healthcare, agriculture, e-commerce, and more.

Looking ahead, the dream of achieving Artificial General Intelligence (machines as smart as humans) is exciting but still distant. However, AI and machine learning are predicted to generate trillions of dollars in value annually by 2030.

As you learn these skills, you'll discover the vast opportunities machine learning offers in different sectors. The demand for these skills is high, making it an excellent time to dive into machine learning. Stick with the course, and I'm confident you'll find mastering these skills rewarding.

In the next video, we'll delve into a more formal definition of machine learning, explore different types of problems, and introduce key terminology. Let's move on to the next video!