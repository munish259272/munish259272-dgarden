---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/02-supervised-vs-unsupervised-machine-learning/01-what-is-machine-learning/","dg-note-properties":{}}
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

### What is machine learning  (video can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

![01_what-is-machine-learning-20240131103546576.png](/img/user/attachments/01_what-is-machine-learning-20240131103546576.png)

Machine learning is about teaching computers to learn without being explicitly programmed. **Arthur Samuel,** a pioneer, demonstrated this in the 1950s by creating a checkers-playing program. Even though Samuel wasn't skilled at checkers, he programmed the computer to play many games against itself. By learning from wins and losses, the program became better over time, surpassing Samuel's own skills.

![[01_what-is-machine-learning-20240131103731077.png\|01_what-is-machine-learning-20240131103731077.png]]

![[01_what-is-machine-learning-20240131104052302.png\|01_what-is-machine-learning-20240131104052302.png]]

In the following videos, we'll delve into major machine learning types. The primary ones are **<span style="color:#000000">supervised learning</span>** and **<span style="color:#000000">unsupervised learning</span>**. Supervised learning, the most widely used, is covered in the first two courses of this specialization, while the **third focuses on unsupervised learning, recommender systems, and reinforcement learning.**

Practical advice on applying learning algorithms is a significant focus. It's not just about having tools but also knowing how to use them effectively. **<span style="color:#000000">Many experienced teams sometimes struggle due to ineffective approaches</span>**. This class aims to equip you with both tools and skills to avoid such pitfalls.

In the next video, we'll explore supervised and unsupervised learning in more detail, understanding when to use each. See you there!