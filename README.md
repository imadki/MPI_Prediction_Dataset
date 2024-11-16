# MPI_Prediction

## I. Introduction
High-performance computing (HPC) plays a crucial role in tackling complex scientific and engineering challenges, particularly those involving partial differential equations (PDEs). However, HPC simulations that involve PDEs often require extensive communication between the computing nodes, which can slow down the process. In the world of HPC, one of the key tools for communication is the Message Passing Interface (MPI). Optimizing how MPI handles this communication is vital to achieving top-notch performance in PDE simulations.

The challenge, though, lies in the multitude of available MPI algorithms, with the best one depending on various factors like the nature of the problem, mesh size, compiler, problem dimensionality, and communicator characteristics. To overcome this challenge, an innovative approach has emerged: a machine learning-based model designed to predict the optimal MPI algorithm for specific PDE simulations. This model considers several critical parameters related to the simulation, such as the physical problem at hand, mesh size, compiler settings, problem dimensions, and communicator traits

This study underscores the significance of careful selection when it comes to input features and training data, ensuring the model's accuracy and its ability to generalize to a wide range of PDE simulation scenarios. Ultimately, this research represents a significant step forward in the quest for more efficient and effective high-performance computing for PDEs, opening doors to new possibilities in various scientific and engineering domains.
### 1.1 Describe the Data Set
We have a dataset with 23,544 entries and 8 columns. <br>
The columns are as follows: <br>
* MeshSize: An integer column that likely represents the size or granularity of a mesh used in simulations.
* Compiler: A categorical (object) column indicating the type or version of the compiler used in the simulations.
* NumberofVariables: An integer column indicating the number of variables involved in the simulations
* VariableType: A categorical (object) column represents the type of the variables.
* NumberofNodes: An integer column specifying the number of computational nodes used in the simulations.
* NumberofCores: An integer column indicating the number of processor cores used in the simulations.
* Dim: An integer column representing the dimensionality of the simulations.
* Communication: A categorical (object) column .<br>
*-* The objective of this project is to use the first seven columns (MeshSize, Compiler, NumberofVariables, VariableType, NumberofNodes, and NumberofCores,Dim) as features to predict the eight column (Communication)

![Show_num_instant](IMG/Number%20of%20Instances%20per%20Class.jpg)


### 1.2 Data Types
As we noticed in the table bellow , some of our features are strings or objects, so we should convert or encode all the variables to become numerical values.

| Column             | Data Type |
|--------------------|-----------|
| MeshSize           | int64     |
| Compiler           | object   |
| NumberofVariables  | int64     |
| VariableType       | object   |
| NumberofNodes      | int64     |
| NumberofCores      | int64     |
| Dim                | int64     |
| Communication      | object   |
