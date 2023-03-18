# Edge classification with pytorch geometric

Train an Edge Classifier Graph Neural Network to classify the edges (given by the edge_index ) as true or false (given by the array y ). 
The inputs to training/inference are x (the node features) and edge_features. 

## Approach

My approach to this task was as follows:
- Download and load the dataset 
- Explore the data given 
- Get a simple model ready and test it on one graph
- Train the model on the given dataset 
- Expand on the small working example

I have included 2 python notebooks that summarize my approach. The `edge_classification.ipynb` file contains my initial model where I tried to get a sample working but I had not used **edge features** along with **node features** as inputs in training. I had created an Encoder and Decoder which I used for the Edge Classification Task and trained the dataset on 5 epochs to get an accuracy of **91%**

The `edge_classification_final.ipynb` contains my implementation of the edge classification task in which I was able to incorporate **both** edge features as well node features. I used GATConv for the convolution layers and in the forward pass I was able to incorporate edge features in the input for the fully connected layer. I got decent accuracy around **80%**. To demonstrate further, I implemented my own **MessagePassing Network** to use it in the model. While it is not the best design for the message passing layer, I got an accuracy of around **82%** which is similar to the GATConv model used previously. 

The File structure is as follows: 

```
gnn-tracking-task
├── README.md
├── edge_classification_final.ipynb
├── edge_classification.ipynb
```

Thank you!! 
