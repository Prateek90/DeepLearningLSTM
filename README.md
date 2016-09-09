# DeepLearningLSTM

##**RNN Language Model Architecture**

**Dataset**

The dataset being used here is Penn Tree Bank dataset. PTB dataset is a collection of natural English words that form sentences. The dataset consist of 10000 words that are being used in our network.

**Architecture**

The language model applied here in this assignment is GRU (Gated Recurrent Network). GRU are a variation of LSTM(Base Model), it combines forget and input gate of LSTM into a single update gate, GRU also merges cell state and hidden state and makes some other changes. The RNNs can have multiple hidden layers, the output from one layer will be propagated to the next hidden layer and so on until the final hidden layer which is followed by a Linear layer that predicts the probable next word from the vocabulary.

The structure of our network is a s follows:

Look-Up Table --> GRU Module --> Dropout Module --> GRU Module --> Dropout Module --> Linear Module --> LogSoftMax module 


Number of Layers = 2

Batch Size = 10

Sequence Length = 15

Size of input = 200

Vocabulary Size = 10,000


**Training**

The Class NLL-Criterion is used as a loss function so that the output of the network is interpreted as a list of log probabilities. At each time-step one word is fed to the neural network and the next word (one word from the vocabulary) is predicted as the output. The parameters of the network are optimized using back-propagation with following hyper parameters:

Unrolling sequence length = 10

Learning rate = 1

Decay = 2

Dropout = 0.2

Euclidean Norm Clipping = 5

The network was trained for a total of 13 epochs during which weight decay started after 4 epochs

**Results**

Perplexity was used as the error metric and following perplexity was obtained:

Train-Set Perplexity = 114.866

Validation-Set Perplexity = 180.595

Test-set Perplexity=175.695

