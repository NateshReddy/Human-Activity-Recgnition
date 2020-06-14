# Human-Activity-Recgnition
We worked on action recognition in search and rescue using drone surveillance. Our aim was to classify a video on help or non-help class. Which can be used during a disaster as at many places people can’t reach to check if there is any person needing help but the drone can search the area and notify the location to the rescue team.  


## Requirements
This code requires you have Keras 2 and TensorFlow 1 or greater installed. Please see the requirements.txt file. To ensure you're up to date, run:

pip install -r requirements.txt

You must also have ffmpeg installed in order to extract the video files. If ffmpeg isn't in your system path (ie. which ffmpeg doesn't return its path, or you're on an OS other than *nix), you'll need to update the path to ffmpeg in first block of the code in the function extract_files().

## Getting the data
The data set we used was UCF 101 dataset(contained 101 different classes over 13k video clips) and Help Non-Help data set which was collected by the drone by one of our mentors. 

To download the UCF-101 dataset into the data folder:

cd data && wget http://crcv.ucf.edu/data/UCF101/UCF101.rar

Then extract it with unrar e UCF101.rar.

Next, create folders (still in the data folder) with mkdir train && mkdir test && mkdir sequences && mkdir checkpoints.

Now you can run the scripts in the data folder to move the videos to the appropriate place, extract their frames and make the CSV file the rest of the code references. You need to run first block of the code.

## Extracting features
Before you can run the model, you need to extract features from the images with the CNN. This is done by running second and third codeblock in the file. 

## Training models
After extracting the features the next block have to be compiled where the model is defined.

The first which we used was the CNN in which we attempted to classify each video based on a single frame. Also we used Inception V3 which was pretrained on imagenet dataset .(also known as transfer learning)  Now instead of just classifying based on CNN model,we used CNN+RNN. Now the features extracted from inception V3,we convert those extracted features into sequences of extracted features and then are passed to LSTM after removing the top classification layer.on which we got 89.74% of accuracy.
