# Neural_Network_Charity_Analysis

## Overview
This project uses deep learning neural network analysis to model donor contribumtion potential based on on a donor dataset provided by Alphabet Soup Charity.  The model target is to reach an accuracy of 75%.  After the initial starter model was ran, three attempts were made; albeit unsuccessfully to optimize the neural networks nerons, variables, hidden layers, activation functions, and epochs to achieve accuracy over 75%.  

## Resources
  1. **Resources/charity_data.csv** - Donor Dataset
  2. **Checkpoints** - folders containing saved model weights by every 5th epocj.  Version number designated by **optN**. Initial model run has no suffix. 
  3. **AlphabetSoupCharity** - inital model run.  Optimization runs followed by **_Optimization_v0N**
  4. **AlphabetSoupCharity.h5** - saved nueral network model file.  Optimization runs followed by **_Optimization_v0N**

## Results
  * **Data Preprocessing**
    * Target Variables - every model used the **IS_successful** as the target variable
    * Feature Variables
      * Initial Model Features
      ![image](https://user-images.githubusercontent.com/91850824/165209876-c94c324f-f448-4702-9250-ead5342b2524.png)

      * Optimized Features - dropped Income Amount.  Vast majority of all Income Amounts are 0.  It appear likely that the amounts were just not entered and can skew the data; also, valued rows are not specific enough to decipher any real value.
      ![image](https://user-images.githubusercontent.com/91850824/165209901-e8078fe5-2639-48ef-b396-2a8721a64ecf.png)
      ![image](https://user-images.githubusercontent.com/91850824/165210133-7d012486-2dac-48c4-a57a-b39b176b9ac7.png)

    * Variables Removed from Dataset
      * Initial Model Features - EIN and NAME
      * Optimized Features - EIN, NAME, and INCOME_AMT 
     
   * **Compiling, Training, and Evaluating the Model**
    * Model Features
      * Neurons - best attempt used 100 nerons as the max (roughly 3 time the # of features after encoding)
      * Layers - 3 layers appeared give my best results, this was done admittedly through trial and error.
      * Activation Functions - relu returned the best reulsts in the hidden layers.  Sigmoid was used for all output layers.
    * Model Performace - my best otimization achieved 72.97% Accuracy, higher than the initial base 72.4%.
    * Steps to increase model performance
        1. Optimization 1
          1. Drop Income Amount
          2. Added a third hidden layer and increased neurons 
            ![image](https://user-images.githubusercontent.com/91850824/165212829-7c5f316e-8fb2-4b4f-b644-10d19bf0ada2.png)
          3. Increased Epochs to 200
            
        2. Optimization 2
          1. Drop Income Amount
          2. Bucketed Calssification value below 2000 (original was 1500).  Reinterpreted desnity graph
            ![image](https://user-images.githubusercontent.com/91850824/165212695-5bf0b536-8c19-41e5-8a91-064ad7c44bbf.png)
            ![image](https://user-images.githubusercontent.com/91850824/165212710-4e2da7f7-0c31-43c3-b0a4-05d98cf2d0c1.png)
          3.  Bucketted Application Type below 150 (original was 500). Reinterpreted desnity graph.
            ![image](https://user-images.githubusercontent.com/91850824/165213602-3d75da2d-7138-4b3c-93bd-503d031980b3.png)
            ![image](https://user-images.githubusercontent.com/91850824/165213622-aae42bd3-74d3-4e67-b1cc-f994a066ceea.png)
          4. Added a third hidden layer and increased neurons 
            ![image](https://user-images.githubusercontent.com/91850824/165213654-7264b80c-975a-460c-bc22-84d9116e8252.png)
          5. Increased Epochs to 200
        
        3. Optimization 3
          1. Drop Income Amount
          2. Bucketed Calssification value below 150 (original was 1500)
          3. Bucketted Application Type below 100
          4. Added 4th hidden layer, set 4th activation layer to tanh.
          ![image](https://user-images.githubusercontent.com/91850824/165214020-2ce07e3a-f71d-4710-b66c-5d9f073af21f.png)
          5.  Returned to 100 Epochs


## Summary - overall results for deep learning model, reccomendations 

  Overall I improved the base model.  The accuracy results are:
    1.  Initial Model - 72.4%
    2.  Opt 1 - 72.97%
    3.  Opt 2 - 72.5%
    4.  Opt 3 - 72.58%
   
  Many more optimization attempts were performed beyond the three above the prime improvements were made by removing the Income Amount Feature and adding an additional layer, and neurons.  As I added more layers and nerons, the total acuracy decreased from Opt 1.  Using Activation Functions other than relu, in any layer was met with minimal success.  I chose to change actions after each run.
  
An optimization script was also attempted; however, after an hour, the bext accuracy was around 73% and due to time constraints it had to be abandoned.  The optimization lead to the formation of Opt 1.  A layer was added and nerons increased for opt 2, as well as changes to the binning as stated above.  An extra layer was added to Opt 3 and the fourth layer activation was changed to tanh.  Opt 1 was originally changed 1 item at a time with no improvements.  The Opt 2 and 3 as saved in this repository were the last options after hours of optimizatio and trial and error .  Opt 2 and 3 show the non-effect of increased layers and nuerons as well as the altered binning.
  
 Further analysis into this dataset should consider a Random Forest Model approach.  A lot of the data lends itself to a categorical decision tree format and decision trees are designed to group and make the best of weak learners and should perform similarly to neural network analysis.  The biggest advantage is speed of processing, but with the difficulty to improve the initial accuracy, there is a high chance to overfit the data.  All trained accuracies were higher than the accuracies using the tested data.  More features may needed to be removed, or this process may have already tended to overfit.
 
 ![image](https://user-images.githubusercontent.com/91850824/165218402-05435ac4-ad27-4a31-aa6c-1c6e6eeaa2e9.png)
  ![image](https://user-images.githubusercontent.com/91850824/165218414-4b80318e-6aea-4ca0-b76e-2cebd9ca14cf.png)
  ![image](https://user-images.githubusercontent.com/91850824/165218439-fde04ee5-439a-4b3a-8eac-fd916bc6de4d.png)
  ![image](https://user-images.githubusercontent.com/91850824/165218458-04e92788-f0a0-45c4-bf3e-73f781d7f51d.png)





    
