## Social network graph

Social networks can naturally be expressed in the form of a graph, where the nodes represent people and the connections between people, such as friendship or coworkers, is represented by edges. Here is one illustration of such social network. Let's imagine that we have a social network whose members (nodes) are Bill, Terry, Henry, Cary and Alistair etc. The relationship between them are represented by a link (edge), and each person’s interests such as, sports, arts, games and comics are represented by node properties. 

![](assets/social-network.png?raw=true)


## GNN message passing mechanism to generate node embedding
The way a GNN transforms the intial node features to node embeddings, is by a technique called message passing. The process of message passing is illustrated in the figure below. In the beginning, the node attributes/features are converted into numerical attributes. In our case, we do one-hot encoding of the categorical features (Henry’s interests: arts, comics, games). Then, the first layer of GNN aggregates all neighbor’s (Gary and Alistair) raw features (in black) to form a new set of features (in yellow). A common approach is to do linear transformation of all neighboring features, aggregate them through a normalized sum, then pass the results into a non-linear activation function, such as ReLU, to generate a set of new features. The following figure illustrates how message passing works for node *Henry*. The figure below illustrates the computations for Henry and Bill, however, the GNN message passing algorithm will compute representations for all of the graph nodes, which are later used as the input features for the second layer. 



![](assets/message-passing.png?raw=true)

The second layer of GNN repeats the same process, but takes the the previously computed feature (in yellow) as an input from the first layer. The aggregation sums-up all neighbor’s new embedded features (Gary and Alistair), and generate second layer feature vectors for Henry (in orange). As you can see, by repeating the message passing mechanism, we extended the feature aggregation to 2-hop neighbors. In our illustration, we limit ourselves to 2-hop neighbors, but extending into 3-hop neighbors can be done in the same way by adding another GNN layer. 



The final embeddings from Henry and Bill (in orange) are used for computing the score. During the training phase, link score is defined as 1 when the edge exists between two nodes (positive sample), and as 0 when edges between two nodes don’t exist (negative sample). The error or loss between the actual score and the prediction *f(e1,e2)* is then back-propagated into previous layer to adjust the weights in the aggregation function and node embedding. Once the training is finished, we can rely on the embedded feature vectors for each node to compute their link’s score with our function *f.* 


## Train your Graph Convolution Network with Amazon Neptune ML

The figure below illustrates different steps for Neptune ML to train GNN-based recommendation system. You can follow the notebook and try different steps with sample code.  



![](assets/NeptuneML-illustration.png?raw=true)