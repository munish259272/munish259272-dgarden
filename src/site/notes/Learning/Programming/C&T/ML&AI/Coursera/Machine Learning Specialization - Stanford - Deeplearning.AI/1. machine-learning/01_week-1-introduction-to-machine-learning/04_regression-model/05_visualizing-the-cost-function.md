---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/04-regression-model/05-visualizing-the-cost-function/","dg-note-properties":{}}
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

### visualizing the cost function  (video can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

In the last video, we looked at a **cost function**, which is like a score telling us how good our model is at predicting something, in this case, house prices. We have two things to adjust in our model, which we call **parameters** w and b. Our goal is to change w and b to get the lowest score on the cost function, which means our model's predictions are really close to the real prices.

![05_visualizing-the-cost-function-20240131210840620.png](/img/user/attachments/05_visualizing-the-cost-function-20240131210840620.png)
We already saw a simple version with just w when b was set to zero, which made it easier to understand. Now, we're bringing b back, so we have both w and b to work with.

![05_visualizing-the-cost-function-20240131210924831.png](/img/user/attachments/05_visualizing-the-cost-function-20240131210924831.png)
Let's imagine our cost function as a 3D shape, like a **soup bowl**. If the bowl were sitting on a table, the bottom of the bowl, its lowest point, is where we get the best w and b for our model – it's where the cost function score is the lowest.

Each point in the bowl represents a different combination of w and b, and the height of that point tells us the score – the lower, the better.

![05_visualizing-the-cost-function-20240131210938628.png](/img/user/attachments/05_visualizing-the-cost-function-20240131210938628.png)
Now, a **contour plot** is another way to look at this bowl. Imagine slicing the bowl horizontally and looking down from above. Each ring on a contour plot is like a slice of the bowl, showing us points that have the same score.

![05_visualizing-the-cost-function-20240131211011090.png](/img/user/attachments/05_visualizing-the-cost-function-20240131211011090.png)
The very center of the rings, right at the bottom of the bowl, is where we get the best score, the lowest cost function value.

So, to recap, we're trying to find the best w and b for our model by looking for the lowest point in a 3D soup bowl. We can also use a contour plot to help us see where that lowest point is from a top-down view. In the next video, we're going to see how changing w and b changes the line we're trying to fit to our data. Let's check it out!