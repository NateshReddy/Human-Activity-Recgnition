# Human-Activity-Recgnition
We worked on action recognition in search and rescue using drone surveillance. Our aim was to classify a video on help or non-help class. Which can be used during a disaster as at many places people can’t reach to check if there is any person needing help but the drone can search the area and notify the location to the rescue team.  

The data set we used was UCF 101 dataset(contained 101 different classes over 13k video clips) and Help Non-Help data set which was collected by the drone by one of our mentors.  T

he first which we used was the CNN in which we attempted to classify each video based on a single frame. Also we used Inception V3 which was pretrained on imagenet dataset .(also known as transfer learning)  Now instead of just classifying based on CNN model,we used CNN+RNN. Now the features extracted from inception V3,we convert those extracted features into sequences of extracted features and then are passed to LSTM after removing the top classification layer.on which we got 89.74% of accuracy.
