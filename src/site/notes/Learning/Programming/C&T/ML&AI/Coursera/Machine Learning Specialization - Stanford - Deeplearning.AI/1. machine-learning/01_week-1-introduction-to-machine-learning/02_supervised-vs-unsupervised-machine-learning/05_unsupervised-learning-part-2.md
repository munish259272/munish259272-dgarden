---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/02-supervised-vs-unsupervised-machine-learning/05-unsupervised-learning-part-2/","dg-note-properties":{}}
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

### Unsupervised learning part 2 (video can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

In our previous video, we learned about **unsupervised learning**, which is when we only have input data (X) without any given output labels (Y). Our job is to discover patterns or interesting structures in that data. We looked at one kind of unsupervised learning called **clustering**, where we group similar items together.

![05_unsupervised-learning-part-2-20240131124539053.png](/img/user/attachments/05_unsupervised-learning-part-2-20240131124539053.png)
In this course, you'll learn about two more kinds:

1. **Anomaly detection**: This is like a detective finding something out of the ordinary. It's really useful for spotting fraud in banks, where unusual transactions could mean trouble.
    
2. **Dimensionality reduction**: Think of this as packing for a trip. You want to fit everything you need into a smaller suitcase without leaving behind anything important. This method helps to shrink a big dataset down to something smaller but still keeps the important information.
    

If you're not clear on anomaly detection or dimensionality reduction yet, don't worry! We'll cover them later in detail.

![05_unsupervised-learning-part-2-20240131124600490.png](/img/user/attachments/05_unsupervised-learning-part-2-20240131124600490.png)
Now, let's do a quick test. Which of these examples do you think use unsupervised learning?

- **Spam filtering**: If you've got emails tagged as spam or not, that's a supervised learning task since you have labels.
- **Grouping news stories**: Like what Google News does, grouping articles without being told the groups in advance, is an unsupervised learning task.
- **Market segmentation**: This is when you let an algorithm sort customers into groups on its own, also an unsupervised learning task.
- **Diagnosing diabetes**: This is more like the cancer example we talked about, where you know who has diabetes and who doesn't. It's a supervised learning task.

Even though we've focused a lot on clustering, we'll also dive into **anomaly detection** and **dimensionality reduction** in upcoming videos.

And one last thing before we finish this section - I'm excited to show you how **Jupyter Notebooks** can be a great tool for machine learning. We'll take a look at that in the next video.