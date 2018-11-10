# Writing Bach Style Music with Deep Learning LSTM model

This project uses an LSTM deep learning network to write music in Bach's style.The network is trained on Bach fugues from the Well-Tempered Clavier, and then the network outputs a series of musical notes. This is a similar process to text generation using an LSTM network. MIDI notes are treated as a series of words for training the network. The network uses the previous 50 MIDI notes to predict the next MIDI note.

To create music, a random seed is chosen from the training set. Every time the algorithm runs, the results are somewhat different. Sometimes the results get stuck playing a repetitive series of notes over and over again. It could be interesting to count these pattern and then force the model to start with a new seed. 

The output was then imported in a DAW (Digital Audio Workstation) where everything was forced into Cmajor. You can hear the results here on youtube [https://www.youtube.com/watch?v=uh3myqiX7es](https://www.youtube.com/watch?v=uh3myqiX7es)

# Files
* Bach_well_tempered.ipynb - code for downloading data, cleaning data, training model, and outputting results
* 2018-11-09 16/45/04.528977-50-0.9791.hdf5 - trained model that can be used instead of running the code to train from scratch
* example1.mid, example2.mid, example3.mid - example midi output
* example.mp3 - example1.mid forced into Cmajor and played with piano

# Getting Started
These instructions will get you a copy of the project up and running on your local machine.

### Prerequisites
You will need the following Python packages:
* requests
* copy 
* pathlib
* music21
* os
* pandas
* matplotlib
* numpy
* keras
* tensorflow
* jupyter

Many of these packages come with an Anaconda installation, so it's suggested to [install anaconda](https://www.anaconda.com/download/). 

Installation instructions for music21 can be found [here](http://web.mit.edu/music21/doc/installing/index.html). And Keras instructsions are at [this link](https://keras.io/#installation).

### Installing

Other than the pre-requisite Python package, there is nothing else to install. 

### Running the Code

You can run the Jupyter Notebook locally to download the necessary files, prepare the data, train the model, and output new music.

Note that to download the necessary MIDI files, uncomment the second code cell in the Jupyter notebook.

The last cell in the code will output a MIDI file of the results. You can then use the MIDI file in another program to play the results or add instrumentation.

# Ideas for Further Development
* vary the sequence length for training. Currently the sequence length is 50
* try smaller batch size, which is currently 32
* transpose all training sets into the same starting key
* create a major model and a minor model for different fugues

# Acknowledgements
[Text Generation With LSTM Recurrent Neural Networks in Python with Keras
](https://machinelearningmastery.com/text-generation-lstm-recurrent-neural-networks-python-keras/)