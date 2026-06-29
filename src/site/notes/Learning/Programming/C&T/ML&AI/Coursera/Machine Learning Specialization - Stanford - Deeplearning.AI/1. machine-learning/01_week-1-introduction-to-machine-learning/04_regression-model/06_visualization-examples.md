---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/04-regression-model/06-visualization-examples/","dg-note-properties":{}}
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

Let's make this simpler. When we're using machine learning to draw a line through data, we use two numbers: **w** (weight) and **b** (bias). Together, they decide where and how the line will appear on a graph.

First, imagine you have a graph, and you're trying to draw a line that fits well with a set of points, like trying to draw the best path through stars in the sky. The line's **slope** is determined by **w**, and where it hits the y-axis (up and down) is set by **b**.

![06_visualization-examples-20240131213545520.png](/img/user/attachments/06_visualization-examples-20240131213545520.png)
Now picture a point on the graph labeled **j**. If **w** is about **-0.15** and **b** is about **800**, this means the line slants downward (because of the negative **w**) and crosses the y-axis really high up (because **b** is 800).

But if this line is way off from where the actual data points are, it means the **w** and **b** we chose aren't great. It's like guessing the path through the stars and being way off. This mistake has a cost, a penalty for being wrong. On a special graph that shows us this cost, called a **cost function**, this choice is far from the best spot, which means it's a high-cost, bad choice.

Let's take another example. If **w** is **0** and **b** is **360**, the line will be flat (horizontal) because **w** is zero (no slope), and it will touch the y-axis at 360. It's still not perfect, but maybe a bit closer to the points than our first try.

![06_visualization-examples-20240131213637615.png](/img/user/attachments/06_visualization-examples-20240131213637615.png)
We can keep trying different **w** and **b** values, and each time we'll get a different line. Some lines will be closer to the points, and some will be farther. The closer we are to the points, the closer we'll be to the center of a special shape, an **ellipse**, on our cost graph. That center is where the cost is the lowest – it's our best guess.

When we find a line that goes pretty well through the points, it means we're close to the lowest cost, which is our goal.

In the optional lab, you can play with this yourself. You can move a slider or click on a graph to change **w** and **b** and see how the line moves and what the cost looks like. It's like a game to find the best path through the stars.

But in real machine learning, we don't guess. We use a clever method called **gradient descent**. This helps us find the best **w** and **b** without guessing. It's like having a smart friend who's really good at finding paths through the stars.

Gradient descent is super important because it's not just for drawing lines; it helps with many kinds of machine learning problems, even very complicated ones.

In the next video, we'll dive into gradient descent and see why it's such a big deal in machine learning.