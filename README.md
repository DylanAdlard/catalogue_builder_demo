# Catalogue Builder Method

A class to build mutation catalogues using the binary Fisher's test

## Introduction

This method relies on the logic that mutations that do not cause resistance can co-occur with those that do, and if a mutation in isolation (solo) does not cause resistance, then it will also not contribute to the phenotype when not in isolation.

Mutations in specified genes are traversed in sequence, and a Fisher's test is run on the binary phenotype distributions of their solos. Mutations are therefore charactserised as benign if there are stastisitcally more susceptible samples carrying only that mutation across the relevant candidate genes than resistant samples also carrying only that mutation. If the null hypothesis is accepted, an unknown (U) phenotype is called. Following characterisation as benign, that mutation is removed from the dataset to potentially proffer additional solos for classification. The run is then repeated with the updated dataset until either there are no susceptible samples, or no remaining mutations exist in isolation.

The catalogue can either be returned as a dictionary, or as pandas dataframe which can be saved as a Piezo compatible csv.

![Protocol](https://github.com/DylanAdlard/catalogue_builder_demo/imgs/protocol.png)

## Getting Started

`conda create --name myenv --file requirements.txt`

(although the only dependencies outside of the Python Standard Library are pandas and Piezo)

`conda activate myenv`

Sample code for data preperation and running `BuildCatalogue()` can be found in the demo.ipynb notebook.
