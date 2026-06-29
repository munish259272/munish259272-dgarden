---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/04-regression-model/04-cost-function-intuition/","dg-note-properties":{}}
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

### cost function intuition  (video can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

Let's understand what a **cost function** does in machine learning, especially when we're using it to find the best settings for our model.

Imagine you're trying to draw a straight line through a set of points on a graph. These points are our training data. The line is our model's guess at the pattern in the data. The closer the line is to the points, the better our model's guess.

We control the line with two knobs: **w** (weight) and **b** (bias). Turning these knobs changes the angle and position of the line. The cost function is like a guide that tells us how good or bad our line is. It gives us a number (the cost) that's smaller when our line is close to the points and bigger when it's far away.
![04_cost-function-intuition-20240131185851846.png](/img/user/attachments/04_cost-function-intuition-20240131185851846.png)

To make things simpler, let's just focus on **w** and forget about **b** for now. So our model is just **fw(x) = w * x**. If we choose **w** to be 1, our line goes right through all the points, which is perfect! The cost function gives us a cost of 0, which is as low as it can go.

![04_cost-function-intuition-20240131185922495.png](/img/user/attachments/04_cost-function-intuition-20240131185922495.png)

But what if **w** is 0.5? The line doesn't hit all the points perfectly anymore. There's some space between the line and the points. The cost function measures these spaces (errors) and gives us a number. For **w** at 0.5, this number (the cost) is about 0.58, which is worse than 0.

Now, what if **w** is 0? The line just lies flat on the x-axis, and it's even further from the points. The cost function gives us an even higher number: about 2.33.

![04_cost-function-intuition-20240131185949033.png](/img/user/attachments/04_cost-function-intuition-20240131185949033.png)

We can keep trying different values for **w**, even negative ones. Each time, we get a new line and a new cost from the cost function. If we plot these costs for each **w**, we get a curve that shows us how good each **w** is.

![04_cost-function-intuition-20240131190051657.png](/img/user/attachments/04_cost-function-intuition-20240131190051657.png)

Our job is to find the **w** that gives us the lowest cost because that's the line that fits our data best. In our example, **w** at 1 made the cost function hit 0, which was perfect. That's what we aim for in linear regression: the smallest possible cost, which means our model's line is the best fit for the data.

![04_cost-function-intuition-20240131190101828.png](/img/user/attachments/04_cost-function-intuition-20240131190101828.png)

In summary, we use the cost function to tell us how to adjust **w** (and **b** in more complex models) to get the best line through our data. The goal is to make the cost as small as possible, and that's how we train our model in linear regression. In the next video, we'll see how this works when we use both **w** and **b** and look at some cool 3D plots that show us the cost for different combinations of **w** and **b**.