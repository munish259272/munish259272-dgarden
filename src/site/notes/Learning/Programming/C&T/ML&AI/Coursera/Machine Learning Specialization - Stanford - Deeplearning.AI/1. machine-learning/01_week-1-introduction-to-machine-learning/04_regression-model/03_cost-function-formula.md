---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/04-regression-model/03-cost-function-formula/","dg-note-properties":{}}
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

### cost function formula
```run-python
play_video("00:00:00")
```
Alright, let's simplify this discussion about the **cost function** in machine learning, specifically for linear regression.

When we do machine learning, especially linear regression, we're trying to draw a line through a set of points. We have a **formula** for this line, which is usually written like this: f(x) = wx + b. Here, w and b are the line's **slope** and **intercept**, and they're what we're trying to figure out to get the best line possible.
![03_cost-function-formula-20240131160530016.png](/img/user/attachments/03_cost-function-formula-20240131160530016.png)


Imagine we're trying to fit this line to some dots on a graph. We might try different slopes (w) and intercepts (b) to see which line fits best. But how do we know which is best? That's where the **cost function**, often called J, comes in.


The cost function measures how far off our line is from the actual points. It does this by looking at the vertical distance from each point to the line, squaring that distance, and adding them up. We square these distances to make sure we're not mixing up ups and downs.

Here's the key: **We want to make J as small as possible**. When J is small, our line is close to the points, which means it's a good fit.

Let's imagine a simple situation where b is 0. This means our line will go through the origin (where the x-axis and y-axis cross). Now, our formula is just f(x) = wx.

If we pick w to be 1, and all our points are along the line y=x (like (1,1), (2,2), (3,3)), our line fits perfectly! So, J would be 0, which is as small as it can get.

But if w is not perfect, like 0.5 or 0, our line won't go through all the points, and J will be bigger than 0. The bigger J is, the worse our line fits.

For any value of w we choose, we can plot how big J is. If we do this for lots of values, we'll get a curve that shows us how J changes as we change w.

When we look at this curve, we're looking for the lowest point because that's where J is smallest. That point tells us the best value for w. In our simple example, the best w is 1 because that's where J is 0.
![03_cost-function-formula-20240131160623616.png](/img/user/attachments/03_cost-function-formula-20240131160623616.png)
![03_cost-function-formula-20240131160741361.png](/img/user/attachments/03_cost-function-formula-20240131160741361.png)

In real situations, we have both w and b to worry about, which means our cost function is more like a landscape with hills and valleys. We're still looking for the lowest valley, but now we have to explore in two directions, w and b, to find it.

In the next video, we'll look at this landscape and see how we can find the lowest point, which tells us the best slope and intercept for our line.

Remember, the goal of all this is to get the best line through our points, which means finding the w and b that make our cost function J as small as possible.


## <div style='text-align:center'><hr/><h2>OBSIDIANTOANKI ANKIBRIDGE</h2><hr/></div>

TARGET DECK: ML&AI :: ML
FILE TAGS: ML::LinearRegression

<!---->
1\_01\_03 : What is the formula for cost function in linear regression ? #flashcard 
cost function
$$
\Large{
J(w, b) = \frac{1}{2m}\sum\limits_{1}^{m}{ ({\hat{y}}^{i}- y^{i})^2 }
}
$$
<!--ID: 1782523573656-->
<div style="border-top: 4px solid black; margin: 16px 0;"></div>

