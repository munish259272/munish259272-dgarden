---
{"dg-publish":true,"permalink":"/learning/programming/c-and-t/ml-and-ai/coursera/machine-learning-specialization-stanford-deeplearning-ai/1-machine-learning/01-week-1-introduction-to-machine-learning/02-supervised-vs-unsupervised-machine-learning/02-supervised-learning-part-1/","dg-note-properties":{}}
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

### Supervised learning part 1 (video can be skipped, notes are enough)
```run-python
play_video("00:00:00")
```

![02_supervised-learning-part-1-20240131105459199.png](/img/user/attachments/02_supervised-learning-part-1-20240131105459199.png)
Machine learning is a powerful technology that's making a big impact on our economy. When we talk about machine learning, we often refer to different types, and one of the main types is **supervised learning**. In supervised learning, machines learn to map input data (x) to corresponding output data (y). The special thing about supervised learning is that we provide the algorithm with examples to learn from.

![02_supervised-learning-part-1-20240131105519790.png](/img/user/attachments/02_supervised-learning-part-1-20240131105519790.png)
Imagine teaching a computer to recognize spam emails. You'd show it many examples of emails labeled as either spam or not spam. By learning from these examples, the machine gets better at recognizing spam on its own. This process of giving the algorithm labeled examples is what makes it "supervised."

Let's explore some real-world applications. In online advertising, algorithms predict whether you'll click on an ad based on information about the ad and your behavior. This helps companies show you ads you're more likely to click, generating revenue for them.

Another application is in self-driving cars. The machine learns from images and sensor data to understand the position of other cars, ensuring safe navigation.

![02_supervised-learning-part-1-20240131105613543.png](/img/user/attachments/02_supervised-learning-part-1-20240131105613543.png)
Supervised learning is like teaching a computer to make predictions. For instance, if you want to predict housing prices based on house size, you'd provide the algorithm with data showing house sizes and their corresponding prices. The algorithm learns to make predictions, and you can use it to estimate the price of a new house.

There are two main types of supervised learning problems. One is **regression**, where we predict a number, like predicting house prices. The other is **classification**, where we predict which category something belongs to. For example, classifying emails as spam or not spam is a classification problem.

**<span style="color:#000000">In summary, supervised learning is a way to teach machines by showing them examples with correct answers.</span>** It's a powerful tool used in various fields, from advertising to self-driving cars, to make predictions and classifications.