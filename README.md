A natural language processing software to predict the section of a multimer sequence that best maintains tertiary folding; 
A convolutional neural network to predict protein binding affinity from solubility/entropy

Database: Data for the neural network was obtained from the NetMHCII2.3 database

A natural language processing system was designed predict the section of an aligned sequence that would have the highest binding affinity with its substrate counterpart. 
    The model was based on the neural probabilistic language model proposed by Yoshua Bengio, adapted for single character tokens such as amino acid residues rather than words. 
    Each letter character is assigned an integer value. 
    Then joint probability functions are expressed in terms of the given values and word feature vectors are learned simultaneously with the parameters of the probability function.  
    This model was trained on 10,000 amino acid sequences from the NetMHCII2.3 database with a K-score >0.4 in order to identify motifs with high predicted oligomerization capacity. 
25,000 of the aligned sequences provided by the NetMHCII2.3 database were then used to train a 2D convolutional neural network. 
    This created a vectorized 2D array of sequence entropy vs. solubility probabilities. 
    These values were converted into binary vectors using OneHot Encoding. 
    These trained 193-neuron convolutional neural network across three layers and a (kernel size=3). 
