## Amazon Neptune ML Use Cases Workshops
This repository contains code examples for building machine learning on graphs using Neptune ML. The code example covers a few use cases including Fraud Detection and Recommendations.


## What Is Amazon Neptune:
![](credit-card-fraud-detection/assets/knowledge_graph.b0e9408219d92f2ca3c7a05cccf9a5a72e34ddbd.png?raw=true)

Amazon Neptune is a fast, reliable, fully managed graph database service that makes it easy to build and run applications that work with highly connected datasets. The core of Amazon Neptune is a purpose-built, high-performance graph database engine optimized for storing billions of relationships and querying the graph with milliseconds latency. Amazon Neptune supports popular graph models Property Graph and W3C's RDF, and their respective query languages Apache TinkerPop Gremlin and SPARQL, allowing you to easily build queries that efficiently navigate highly connected datasets. Neptune powers graph use cases such as recommendation engines, fraud detection, knowledge graphs, drug discovery, and network security.


## Amazon Neptune ML:
Amazon Neptune ML is a new capability of Neptune that uses Graph Neural Networks (GNNs), a machine learning technique purpose-built for graphs, to make easy, fast, and more accurate predictions using graph data. With Neptune ML, you can improve the accuracy of most predictions for graphs by over 50% when compared to making predictions using non-graph methods.

Making accurate predictions on graphs with billions of relationships can be difficult and time consuming. Existing ML approaches such as XGBoost can’t operate effectively on graphs because they are designed for tabular data. As a result, using these methods on graphs can take time, require specialized skills from developers, and produce sub-optimal predictions.

Using the Deep Graph Library (DGL), an open-source library to which AWS contributes, that makes it easy to apply deep learning to graph data, Neptune ML automates the heavy lifting of selecting and training the best ML model for graph data, and lets users run machine learning on their graph directly using Neptune APIs and queries. As a result, you can now create, train, and apply ML on Amazon Neptune data in hours instead of weeks without the need to learn new tools and ML technologies.

**- Fraud Detection:** in this use case, we use the [IEEE CIS Credit Transations] (https://www.kaggle.com/c/ieee-fraud-detection/data) dataset to build a graph dataset, ingest it in a Neptune DB cluster, build a node classification task to predict if a transaction is fraud by leveraging the different relationships between entities. 


## Environment Setup
All of the examples in this repository assumes that you have a Neptune DB cluster provisioned and running. If you don't have a Neptune DB cluster, you can use a CloudFormation template from here [CloudFormation Template](https://docs.aws.amazon.com/neptune/latest/userguide/get-started-create-cluster.html) to provision a new Amazon Neptune Cluster
## License

This library is licensed under the MIT-0 License. See the LICENSE file.

