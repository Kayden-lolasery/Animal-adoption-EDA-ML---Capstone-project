# Animal-adoption-EDA-ML---Capstone-project
   - Thank you! https://www.kaggle.com/jinbonnie/animal-data/code
![adoption-fee-banner](https://user-images.githubusercontent.com/78312050/123228543-17c25b00-d508-11eb-85fd-d3ca3396b6a8.jpg)
## *Table of contents*
- [Problem Statement](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#problem-statement)
- [Goal](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#goal)
- [EDA interesting points](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#eda-exploratory-data-analysis-interesting-points)
- [Data pre-processing](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#data-pre-processing)
   - [Data cleaning](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#data-cleaning)
      - Missing Values 
   - [Data engineering](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#data-engineering)
      - [Feature Engineering](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#feature-engineering)
         - [Total time spent in shelter](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#total-time-spent-in-shelter)
         - [Adoption rate](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#adoption-rate)
      - [Example of features with data set errors](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#example-of-features-with-data-set-errors)
         - [animalage](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#animalage)
            - [Before & after data-preprocessing](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#before-and-after-data-preprocessing)
- [Label manipulation before training models](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#label-manipulation-before-training-models)
- [ML models used](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#ml-models-used)
- [ML EDA](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#ml-eda)

## Problem statement
- need to maximise adoption rates to ensure adoption shelters are not completely dependent on government funding as well as to improve the quality of life of animals and pet owners.
- This is based off our label: (Adopted, adopted & Returned & Not adopted)
- ![label](https://user-images.githubusercontent.com/78312050/124507050-8dc79b80-ddff-11eb-9634-309278125e00.PNG)

## Goal
- to assist shelters in identifying features to take note of when trying to improve adoption rates.

## EDA (exploratory data analysis) interesting points:
#### Side note: The most notable issue with this dataset is that it does not have any numerical/continuous data for me to manipulate. I must adjust everything to turn them into numbers
- Black cats and dogs have the highest abandon and adoption rates
- ![blackblack](https://user-images.githubusercontent.com/78312050/124514251-29acd380-de0f-11eb-94ed-2c2fd9220218.PNG)
- cats & dogs are the most popular animals to be abandoned
- ![catdog](https://user-images.githubusercontent.com/78312050/124513038-6e833b00-de0c-11eb-9c26-18ab7c7bfe9f.PNG)
- Adoption rate is not time sensitive
- ![not time sensitive2](https://user-images.githubusercontent.com/78312050/124510369-3a0c8080-de06-11eb-855f-a05ba80dcbf3.PNG)
- The most abandoned breed is the domestic shorthair in both cats and dogs (so much so that we can shorten them to a new column)
- ![breednmaes](https://user-images.githubusercontent.com/78312050/124515477-1fd89f80-de12-11eb-91f3-05d4abd46c45.PNG)

# Data pre-processing
## Data cleaning
### Missing values
- Such as deceaseddate, returneddate & identichip indicate alive, not returned and not chipped respectively
- Other items missing will have their entire row dropped
- ![Nans](https://user-images.githubusercontent.com/78312050/124511391-953f7280-de08-11eb-9683-ec06499a0bbc.PNG)
## Data engineering
- Data needs to be in numbers for the Machine to read, these numbers shoud also make sense in the real world. 
### Feature engineering
#### Total time spent in shelter
   - getting **Total time spent in shelter** with intake and movement date
   - ![movein](https://user-images.githubusercontent.com/78312050/124500047-a466f600-ddf1-11eb-9013-6921c74c396d.PNG)
   - ![timespent](https://user-images.githubusercontent.com/78312050/124503961-260e5200-ddf9-11eb-95ef-93b11234ca49.PNG)
   -  **Negative** timing is due to the same day dates being reversed is terms of newer and older dates. easily solved with abs() function
   - ![time spent in shelter](https://user-images.githubusercontent.com/78312050/124504257-acc32f00-ddf9-11eb-8600-d3a9a83e31f4.PNG)
#### Adoption rate
   - Obtained via dividing current adopted with total number of animals. Caveat is that first few entries will be very skewed and jumpy on the graph
      - ![not time sensitive](https://user-images.githubusercontent.com/78312050/124508710-0714bd80-de03-11eb-88fc-62900b26c1c4.PNG)



### Example of features with data set errors
#### animalage
![sam](https://user-images.githubusercontent.com/78312050/124398735-dd4b9000-dd49-11eb-9381-c6cf2dee0af2.PNG)
- Dataset column is riddled with:
   - **strings** where days, weeks & months need to be converted into years
      - *Regular expression* usage to achieve this
   - **outlier errors** which need to make sense. Data that is on extreme ends can affect certain ML models 
      - *better to keep the data's SD relatively low*
      - Here i chose to replace the outlier age (100 year old cats/ dogs) with the googled average maximum age of a cat/dog
![regular expression](https://user-images.githubusercontent.com/78312050/124397544-f7ce3b00-dd42-11eb-8568-a1306e6e95d2.PNG)

### Before and after data-preprocessing
![age product](https://user-images.githubusercontent.com/78312050/124398208-1afae980-dd47-11eb-8f74-2de304e5754d.PNG)
![Capture](https://user-images.githubusercontent.com/78312050/124480640-12072800-ddda-11eb-85e0-94b6e83902fd.PNG)

## Label manipulation before training models
   - SMOTEtomek was chosen to remove the nearest neighbours smoted to ensure data is not to0 cluttered
   - ![labells](https://user-images.githubusercontent.com/78312050/124515730-bb6a1000-de12-11eb-8e96-688565011601.PNG)

## ML models used
Utilizing various Machine learning algorithmns and libraries to get the best model 
![Decision-Trees-Root-Node](https://user-images.githubusercontent.com/78312050/123955411-27481500-d9dc-11eb-91a8-321f66414e67.png)
![images (1)](https://user-images.githubusercontent.com/78312050/123228726-44767280-d508-11eb-91d5-7b23c811a19c.png)
![1523957272561](https://user-images.githubusercontent.com/78312050/123955599-637b7580-d9dc-11eb-9368-b50355d5b7fb.jpg)
## ML EDA
   - MIP plot (we can see that the top 4 features that affected the Model the most were:
      - returned reason
      - Time spent in shelter
      - chipped or not 
      - animal's age
   - ![MIP](https://user-images.githubusercontent.com/78312050/124515648-8231a000-de12-11eb-9112-6d98c575c5e4.PNG)
   - Ultimately the Support vector Machine model was the best:
   - ![scores](https://user-images.githubusercontent.com/78312050/124566365-8f33ab00-de75-11eb-9b45-448f2ed5b247.PNG)
      - 100% recall on adopted & not adopted labels
      - 100% precision on adopted & returned label
      - ![cm](https://user-images.githubusercontent.com/78312050/124516960-6da2d700-de15-11eb-81ae-ab46bf4744de.PNG)
      - ROC OVO (micro on graph) 98%
      - log loss very very low at 0.119 where logloss = 1.1 is when i myself randomly choose and label the data without any model.
      - ![roc](https://user-images.githubusercontent.com/78312050/124517213-020d3980-de16-11eb-8a5f-fab5324e18b6.PNG)


