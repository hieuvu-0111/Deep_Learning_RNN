# Recurrent Neural Network (RNN) {-}

This notebook is adapted from a Deep Learning course assignment which is designed to help students understand how recurrent neural networks are applied to a text classification task using the IMDB movie review dataset. We will go through the complete workflow, including loading the dataset, analyzing and preprocessing text data, building different RNN based models, and evaluating their performance. By experimenting with GRU, LSTM, and bidirectional variants, we will gain practical insight into how different RNN architectures affect classification accuracy and runtime efficiency. The tasks include:

1.  **Coding tasks:** 

    1.1 Analyze and preprocess the dataset to make it suitable for training RNN based models.  

    1.2 Build an RNN model using GRU (Gated Recurrent Unit, https://www.tensorflow.org/api_docs/python/tf/keras/layers/GRU) instead of LSTM, following the demo code provided. Train the model and evaluate its performance on the test set.  

    1.3 Build an RNN model using Bidirectional LSTM (BiLSTM, https://www.tensorflow.org/api_docs/python/tf/keras/layers/Bidirectional). Train the model and evaluate its performance on the test set.  

    1.4 Build an RNN model using Bidirectional GRU (BiGRU, https://www.tensorflow.org/api_docs/python/tf/keras/layers/Bidirectional). Train the model and evaluate its performance on the test set.  

    1.5 Compare the models built in this assignment, including LSTM, GRU, BiLSTM, and BiGRU, in terms of classification accuracy and runtime efficiency. Discuss your observations and explain the performance differences among these model variants.  

2.  **Open discussion questions:** 

    2.1 During preprocessing, text is converted into sequences of integers. Discuss how the choice of vocabulary size and handling of rare words can affect both model performance and generalization on unseen reviews.  
    2.2 Bidirectional RNNs process sequences in both forward and backward directions. Discuss how this bidirectional context can improve sentiment classification and provide examples of review patterns where this might be especially helpful.  
    2.3 Is the IMDB dataset class imbalanced, and how does its class distribution influence the selection of evaluation metrics? In your opinion, which evaluation metrics should be used to better understand the model’s performance, and why?  
    2.4 Sequence length truncation is often applied to limit computational cost. Discuss the trade off between keeping longer sequences for richer context and truncating them for faster training and lower memory usage.  
    2.5 Based on your overall findings, propose improvements or extensions to this assignment. These may include architectural changes, different preprocessing strategies, or alternative evaluation methods, and explain how they could lead to better sentiment classification performance.  


The dataset we will be working on is imdb_reviews. This dataset is a large movie review dataset. This dataset is for binary sentiment classification containing a set of 25,000 highly polar movie reviews for training, and 25,000 for testing. All the reviews have either a positive or negative sentiment. Reference: http://ai.stanford.edu/~amaas/data/sentiment/

Each data sample contains:
- label (tf.int64)
- text (tf.string)
