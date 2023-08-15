# Alphabet Soup Funding 

  Deep Learning - Machine Learning & Neural Networks



## Analysis Overview

Alphabet Soup is a nonprofit foundation seeking a tool that can help select applicants for funding with the best chance of success in their ventures. 

From the dataset, the features are used to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup.

## Dataset
The csv dataset contains over 34,000 organisations that have received funding from Alphabet Soup over the years.

*   The dataset contains a number of columns that capture metadata:

          EIN and NAME — Identification columns
          APPLICATION_TYPE — Alphabet Soup application type
          AFFILIATION — Affiliated sector of industry
          CLASSIFICATION — Government organisation classification
          USE_CASE — Use case for funding
          ORGANIZATION — Organisation type
          STATUS — Active status
          INCOME_AMT — Income classification
          SPECIAL_CONSIDERATIONS — Special considerations for application
          ASK_AMT — Funding amount requested
          IS_SUCCESSFUL — Was the money used effectively

* The "IS SUCCESSFUL" column indicates if the applicant was successful in their venture.

      Column Values:
                    0 = Unsuccessful Venture
                    1 = Successful Venture


### 1. Preprocess the Data
- Define target/s and features for the model

            Target: y = "IS_SUCCESSFUL" column
          Features: X = remaining columns
   

2. Compile, Train, and Evaluate the Model

      * Neural network model is created with TensorFlow and Keras
      * Number of input features and nodes for each layer assigned
      * Hidden layers and output layer established with respective activation functions
      * Compile and train the model
      * Evaluate model performance with loss and accuracy results
   
3. Optimise the Model
    Optimise the model to achieve a target predictive accuracy higher than 75%.

     * Adjust the input data
     * Add neurons to hidden layer
     * Add hidden layers
     * Use different activation functions for hidden layers.
     * Add or reduce epochs 



## Results
Data Preprocessing

What variable(s) are the target(s) for your model?
What variable(s) are the features for your model?
What variable(s) should be removed from the input data because they are neither targets nor features?
Compiling, Training, and Evaluating the Model

How many neurons, layers, and activation functions did you select for your neural network model, and why?
Were you able to achieve the target model performance?
What steps did you take in your attempts to increase model performance?

            
  
    

### Optimisation
       Accuracy - 
       Hidden layers - Ratio of correct positive predictions 
       nodes - Ratio of correct actual positives
       activation - represents overall performance of Precision & Recall
       Epochs - % of correct prediction overall of true pos/neg    


    
### Model #1
      Hidden layers
                1st: nodes = 50 / activation = relu
                2nd: nodes = 40 / activation = relu
                3rd: nodes = 60 / activation = relu
                4th: nodes = 30 / activation = relu
      Epochs: TBA
   -             Accuracy: TBA
                                
### Model #2   

**Optimisation Techniques Employed:**

     Input data
           Dropped additional columns:
           "AFFILIATION","USE_CASE","SPECIAL_CONSIDERATIONS"
           
     Hidden layers
           Alternate activation function for hidden layers
           1st: nodes = 80 / activation = tanh
           2nd: nodes = 30 / activation = tanh
           
     Increased number of epochs to training regimen
           Epochs: 200

  
   -           Accuracy: 65.38%
        -       Target Model Performance: NOT ACHIEVED 
     
### Model #3 
     Hidden layers
                1st: nodes = 50 / activation = relu
                2nd: nodes = 40 / activation = relu
                3rd: nodes = 60 / activation = relu
                4th: nodes = 30 / activation = relu
     Epochs: 80 
   -             Accuracy: 72.43%                 
                         

## Summary
Summarise the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and then explain your recommendation.

-----
### References
Data for this dataset was obtained by edX Boot Camps LLC, from the IRS. Tax Exempt Organization Search Bulk Data Downloads. https://www.irs.gov/



   
