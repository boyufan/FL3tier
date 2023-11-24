# SAFI

Implementation of federated learning on real-world setting in Java.

## Overview
We implement a real-world federated learning project based on Java. There are one server and many clients to 
collaboratively train a model. We use DL4J as the deep learning library. The data we use is a Human 
Activity Recognition (HAR) dataset.

## Server-side
```
main
└─ java
       ├─ baselinemodel.java
       └─ server
              ├─ FederatedModel.java
              ├─ FileServer.java
              └─ ServerConnection.java
```
The base model is a MLP composed of one input layer, one output layer and one hidden layer with 1000
units using ReLU activation. The model can be changed in FederatedModel.java.

FileServer.java is the main file to start the server, after running this file, a FL server is started. FederatedModel.java is used to initialize FL model, define the FL aggregation strategy, and evaluate the model. ServerConnection.java is incharge of network connection, which can be kept without changing.

## Client-side
```
main
└─ java
       ├─ FileClient.java
       ├─ MultiClients.java
       └─ localUpdate.java
```

FileClient.java is used to create a FL client. In the main function, make sure to set the server IP to make sure the client can connect to the server. localUpdate.java is used to input the data and train the model. 

## Communication
Considering there are no enough client devices to do experiments, we use java multithreading to 
simulate the real clients, for example, run 100 threads in one device. If you have the many real devices,
the project also works.

## Reference
https://github.com/Cautiousss/federated-learning
