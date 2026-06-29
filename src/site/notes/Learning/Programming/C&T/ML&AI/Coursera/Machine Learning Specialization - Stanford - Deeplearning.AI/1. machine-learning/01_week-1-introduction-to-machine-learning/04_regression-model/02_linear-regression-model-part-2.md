---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/04-regression-model/02-linear-regression-model-part-2/","dg-note-properties":{}}
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

### linear regression model part 2  (video can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

**<span style="color:#000000">Supervised learning is like having a teacher who gives you the answers while you learn. The "teacher" here is the dataset with correct answers</span>**, like a list of house sizes with their prices.

![02_linear-regression-model-part-2-20240131153121684.png](/img/user/attachments/02_linear-regression-model-part-2-20240131153121684.png)
Here's how it goes:

1. You start with a **training set** that includes **input features** (like house size) and **output targets** (like house price). The output targets are the "correct answers."
    
2. The **supervised learning algorithm** takes this training set and comes up with a **function** (we'll call it f). This function is like a formula that helps you predict new answers based on the inputs.
    
3. When you have a new house size (we call this new input x), you put it into your function f, and it gives you a prediction of the price (we call this y-hat or $\large{\hat{y}}$).
    
4. The actual function f is your **model**, and the values it uses to make predictions are based on w and b, which are just numbers the model adjusts to get as close as possible to the correct answers.
    
5. If we plot the house sizes and prices on a graph, the function f draws a **best-fit line** (a straight line that best represents all the data points). This line is a **linear function** and looks something like this: $\large{f(x)=wx+b}$, where w is the slope and b is where the line crosses the y-axis.
    
6. This type of model is called **linear regression**. When there's only one input feature (like house size), it's known as **univariate linear regression**.
    
7. Later on, you might learn about more complex models that use more than one input, like house size and number of bedrooms. That's called **multivariate linear regression**.
    
8. To make the model as accurate as possible, you need a **cost function**. This tells you how far off your predictions are from the actual prices. The goal is to make this cost as low as possible.
    

That’s the basics of how supervised learning works! It's like fitting the best line through a set of data points so you can make good guesses on new data. Next, we'll learn about the cost function and how it helps us fine-tune our model.