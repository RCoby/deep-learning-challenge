# Alphabet Soup Funding 

  Deep Learning - Machine Learning & Neural Networks

----

## Analysis Overview

Alphabet Soup is a nonprofit foundation seeking a tool that can help select applicants for funding with the best chance of success in their ventures. 
From the dataset, the features are used to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Dataset
   The csv dataset contains over 34,000 organisations that have received funding from Alphabet Soup over the years.
>  Metadata captured in columns:
> 
>                    EIN and NAME — Identification columns
>                APPLICATION_TYPE — Alphabet Soup application type
>                     AFFILIATION — Affiliated sector of industry
>                  CLASSIFICATION — Government organisation classification
>                        USE_CASE — Use case for funding
>                     RGANIZATION — Organisation type
>                          STATUS — Active status
>                      INCOME_AMT — Income classification
>          SPECIAL_CONSIDERATIONS — Special considerations for application
>                         ASK_AMT — Funding amount requested
>                   IS_SUCCESSFUL — Was the money used effectively
>
> The "IS SUCCESSFUL" column indicates the success of each applicant's venture:
>
>      0 = Unsuccessful Venture
>      1 = Successful Venture

## Method 
### Data Preprocessing 
> Target/s and features for model:
> 
>      Target: y = "IS_SUCCESSFUL" column
>      Features: X = remaining columns
>    
> Columns removed which are neither targets nor features:
> 
>      Identification columns
>        EIN
>        NAME

### Compile, Train, and Evaluate the Model
> - Create Neural network model with TensorFlow and Keras 
> - Assign number of input features and nodes for each layer
> - Create hidden layers and output layer with respective activation functions
> - Compile and train the model
> - Evaluate model performance with loss and accuracy results
   
### Model Optimisation 
> Optimise the model to achieve a target predictive accuracy higher than 75%: 
> * Adjust the input data
> * Add neurons to hidden layer
> * Add hidden layers
> * Use different activation functions for hidden layers.
> * Add or reduce epochs 

## Results

Compiling, Training, and Evaluating the Model

- How many neurons, layers, and activation functions did you select for your neural network model, and why?
            
    

### Optimisation
     
       Hidden layers - made of nodes layers process data to identify patterns for making pretictions.
               Nodes - unit within a neural network
                       (takes input values, performs operations and produces an output to pass to next node) 
          Activation - mathematical function applied to the output of a node 
               Epoch - count of complete passes through training dataset 
            Accuracy - % ratio of correct predictions to the total number of predictions
                Loss - % discrepancy between predicted values and actual targets
                
    
### Model #1 Optimisations
> **Hyperparameter options selected by Kerastuner**
> 
>   - Hidden layers
>     
>           -   1st: nodes = 52 / activation = relu
>           -   2nd: nodes = 52 / activation = relu
>           -   3rd: nodes = 64 / activation = relu
>   - Epochs
>
>           -   Epochs: 8
>
>       **Loss: 55.16%**
>     
>       **Accuracy: 73.05%**
> 
> ###    *75% Target Model Performance: **NOT ACHIEVED***
>      
>                                
 ### Model #2 Optimisations
> 
>   - Input data
>     
>         Dropped additional columns:
>          -    AFFILIATION
>          -    USE_CASE
>          -    SPECIAL_CONSIDERATIONS
>   - Hidden layers
>   
>         Alternate activation function for hidden layers:
>          -   1st: nodes = 80 / activation = tanh
>          -   2nd: nodes = 30 / activation = tanh
>   - Epochs
>     
>         Increased number of epochs
>          -   Epochs: 200
>
>       **Loss: 61.67%**
>     
>       **Accuracy: 65.38%**
>     
>        75% Target Model Performance: **NOT ACHIEVED**
> 
>     
### Model #3 Optimisations
> 
>   - Input data
>     
>         Adjusted binning parameters:
>          -    CLASSIFICATION 
>          
>   - Hidden layers
>
>         Added hidden layer & adjusted nodes:
>                1st: nodes = 50 / activation = relu
>                2nd: nodes = 40 / activation = relu
>                3rd: nodes = 60 / activation = relu
>                4th: nodes = 30 / activation = relu
>    - Epochs
>     
>          Decreased number of epochs
>           -   Epochs: 80
>              
>       **Loss: 57.94%**
>     
>       **Accuracy: 72.43%**
>     
> ###    *75% Target Model Performance: **NOT ACHIEVED***
>                          

## Summary
Summarise the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.

-----
### References
Data for this dataset was obtained by edX Boot Camps LLC, from the IRS. Tax Exempt Organization Search Bulk Data Downloads. https://www.irs.gov/



   
