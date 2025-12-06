# Analyzing Students’ Actual Use of E-Learning Systems Using Bayesian Networks
This project builds a Bayesian Network to examine how different factors influence students’ acceptance and actual use of online education. The network structure is inspired by a validated extended Technology Acceptance Model, confirmed via Structural Equation Modeling, to better understand direct and indirect relationships between variables.

## Bayesian Network Structure

The BN includes nodes such as:

-   **COVID_Impact (COV)**
-   **Compatibility (COM)**
-   **Information_Quality (IQ)**
-   **System_Quality (SQ)**
-   **Student_Comp_SelfEfficacy (SCSE)**
-   **Perceived_Ease_of_Use (PEOU)**
-   **Perceived_Usefulness (PU)**
-   **Behavioral_Intention (BI)**
-   **Actual_Use (AU)**

Example of the parent--child relationships defined:

    COVID_Impact → Perceived_Ease_of_Use
    Compatibility → Perceived_Ease_of_Use
    System_Quality → Perceived_Ease_of_Use
    ...
    Perceived_Usefulness → Behavioral_Intention
    Perceived_Ease_of_Use → Behavioral_Intention
    Behavioral_Intention → Actual_Use

These relationships reflect causal assumptions grounded in technology
acceptance research[^1].

## Workflow
1. Preprocessing Data

   - Loading initial data
   - Calculating composite scores for each variable
   - Binning likert-scale values into Low (0), Medium (1), High (2) states.
   
2. Calculating Conditional Probability Tables (CPTs)

   - Estimating prior and conditional probabilities using *Maximum Likelihood Estimation (MLE)*
   - Handle missing or incomplete data
   
3. Defining the Bayesian Network

   - Specifying the network structure (edges based on SEM results)
   - Adding conditional probability distributions
   
4. Performing Inference

   - Predicting the likelihood of different scenarios using `pgmpy`'s inference engine
   - Running both forward and backward inferences
   
5. Subset Analysis

   - Defining subsets of parent variables for analyzing the influence of different combinations on 'Actual Use'
   - Evaluating combinations of Low, Medium, High states
   - Identify strongest contributors to system use

## How to Run the Notebook

### **Prerequisites**

Install dependencies:

``` bash
pip install pandas pgmpy
```

### **Run**

Use Jupyter Notebook:

``` bash
jupyter notebook BN.ipynb
```
[^1]: Pitts, G., Marcus, V., & Motamedi, S. (2025). Lessons Learned From COVID-19: Acceptance of E-Learning Technologies in Higher Education. Human Factors: The Journal of the Human Factors and Ergonomics Society, 0(0). https://doi.org/10.1177/00187208251372863.
