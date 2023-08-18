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
               Nodes - unit within a neural network
                       (takes input values, performs operations and produces an output to pass to next node) 
       Hidden layers - made of nodes, layers process data to identify patterns for making pretictions.
          Activation - mathematical function applied to the output of a node 
               Epoch - count of complete passes through training dataset 
            Accuracy - % ratio of correct predictions to the total number of predictions
                Loss - % discrepancy between predicted values and actual targets      
### Data Preprocessing                
> - Target/s and features for model:
> 
>       Target: y = "IS_SUCCESSFUL" column
>       Features: X = remaining columns
>    
> - Columns removed which are neither targets nor features:
> 
>       Identification columns
>       -  EIN
>       -  NAME
> - Cap unique values in each column at 10
> - Encode categorical values
> - Split the data into training and testing datasets
> - Scale the training and testing features datasets

### Compile, Train, and Evaluate the Model
> - Create Neural network model with TensorFlow and Keras 
> - Assign number of input features and nodes for each layer
> - Create hidden layers and output layer with respective activation functions
> - Compile and train the model
> - Evaluate model performance with loss and accuracy results
>
>      ### **Accuracy: 72.54%** | Loss: 55.95% | Target Model Performance: **NOT ACHIEVED**  
>      ![image](https://github.com/RCoby/deep-learning-challenge/assets/124993623/40fc780a-7246-4476-a366-c44647a01d64)
   
### Model Optimisation 
> Optimise the model to achieve a target predictive accuracy higher than 75%: 
> * Adjust the input data
> * Add neurons to hidden layer
> * Add hidden layers
> * Use different activation functions for hidden layers.
> * Add or reduce epochs 

### Optimisation Model #1
> **Changed Hyperparameter**
>   
>   - Input data
>
>         Decrease the features in the model to minimise noise 
>         Dropped additional columns:
>          -    AFFILIATION
>          -    USE_CASE
>          -    SPECIAL_CONSIDERATIONS
>   - Hidden layers
>   
>         Minimise potential vanishing gradient 
>         Alternate activation function 'Tanh' for hidden layers 
>          -   1st: nodes = 90 / activation = tanh
>          -   2nd: nodes = 60 / activation = tanh
>   - Epochs
>
>         Prevent underfitting / overfitting from too few passes to optimise parameters 
>         Increased number of epochs
>          -   Epochs: 140
>     
>       ### **Accuracy: 65.34%** | Loss: 61.54% | Target Model Performance: **NOT ACHIEVED**  
>       ![image](https://github.com/RCoby/deep-learning-challenge/assets/124993623/4b050009-6f4d-4562-8097-2193793b2202)

### Optimisation Model #2
>  **Changed Hyperparameters**
> 
>   - Input data
> 
>         Binned values prevent outliers skewing the model 
>         Adjusted binning parameters:
>          -    CLASSIFICATION 'Other' cutoff value >200
>          
>   - Hidden layers
>
>         Add hidden layers to increase the number of calculations (made by nodes) to pass on to the next layer
>         Appy diferent activation functions to hidden layers to identify direrent relationships in the data   
>         Added hidden layers 3 and 4 & adjusted nodes:
>          -     1st: nodes = 100 / activation = tanh
>          -     2nd: nodes = 80 / activation = tanh
>          -     3rd: nodes = 90 / activation = relu
>          -     4th: nodes = 70 / activation = relu
>    - Epochs
>
>          Decrease epochs, less passes without being too few 
>          Decreased number of epochs
>           -   Epochs: 80
>       
>        ### **Accuracy: 72.45%** | Loss: 60.1% | Target Model Performance: **NOT ACHIEVED**
>      
>        ![image](https://github.com/RCoby/deep-learning-challenge/assets/124993623/c72acc5c-6034-4fe9-a6db-a3155b5e5ae2)
>
### Optimisation Model #3 
> **Hyperparameter options selected by Kerastuner**
> 
>   - Hidden layers
>     
>           -   1st: nodes = 79 / activation = relu
>           -   2nd: nodes = 67 / activation = relu
>           -   3rd: nodes = 49 / activation = relu
>           -   4th: nodes = 19 / activation = relu
>           -   5th: nodes = 61 / activation = relu
>   - Epochs
>
>           -   Epochs: 150
>
>      ### **Accuracy: 73.03%** | Loss: 55.07% | Target Model Performance: **NOT ACHIEVED**     

## Results
> #### Original Model
>    -    **Accuracy: 72.54%** | Loss: 55.95%
> #### Optimisation Results
>    - Model #1: **Accuracy: 65.34%** | Loss: 61.54%
>    - Model #2: **Accuracy: 72.45%** | Loss: 60.1%
>    - Model #3: **Accuracy: 73.03%** | Loss: 55.07% 

## Summary
> 
> The optimisations models provided the best result, high accuraccy and low loss, when additional hidden layers were added to the model and the activation was exclusively "relu" or a combination of "relu" and "tanh".
> 
> Further model optimisation is recommended as none of the models met the minimum Target Model Performance 75% and the high levels of loss also supports this.
> 
> There are numerous additional optimisation steps yet to be explored in the models, such as Early Stopping based of validation loss.
> This would allow the model to stop training when improvement to loss ceases, to prevent overfitting. 
>
-----
### References
Data for this dataset was obtained by edX Boot Camps LLC, from the IRS. Tax Exempt Organization Search Bulk Data Downloads. https://www.irs.gov/



   
