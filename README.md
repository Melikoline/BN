# Analyzing Students’ Actual Use of E-Learning Systems Using Bayesian Networks
### Overview
This project builds a Bayesian Network to examine how different factors influence students’ acceptance and actual use of online education. The network structure is inspired by a validated extended Technology Acceptance Model, confirmed via Structural Equation Modeling, to better understand direct and indirect relationships between variables.

### Workflow
1. Preprocessing Data

   - Loading initial data
   - Calculating composite scores for each variable
   - Binning likert-scale values into Low (0), Medium (1), High (2) states.
   
2. Calculating Conditional Probability Tables (CPTs)

   - Estimating prior and conditional probabilities using *Maximum Likelihood Estimation (MLE)*
   - Handle missing or incomplete data
   
4. Defining the Bayesian Network

   - Specifying the network structure (edges based on SEM results)
   - Adding conditional probability distributions
   
5. Performing Inference

   - Predicting the likelihood of different scenarios using `pgmpy`'s inference engine
   - Running both forward and backward inferences
   
6. Subset Analysis

   - Defining subsets of parent variables for analyzing the influence of different combinations on 'Actual Use'
   - Evaluating combinations of Low, Medium, High states
   - Identify strongest contributors to system use
