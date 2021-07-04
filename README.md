# Animal-adoption-EDA-ML---Capstone-project
## *Table of contents*
- [Problem Statement](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#problem-statement)
- [Goal](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#goal)
- [Data pre-processing](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#data-pre-processing)
   - Data engineering
      - [Example of features with data set errors](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#example-of-features-with-data-set-errors)
         - [animalage](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#animalage)
            - [Before and after data-preprocessing](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#before-and-after-data-preprocessing)
- [ML models used](https://github.com/lolasery/Animal-adoption-EDA-ML---Capstone-project/blob/main/README.md#ml-models-used)

## Problem statement
- need to maximise adoption rates to ensure adoption shelters are not completely dependent on government funding as well as to improve the quality of life of animals and pet owners
## Goal
- to assist shelters in identifying features to take note of when trying to improve adoption rates.

![adoption-fee-banner](https://user-images.githubusercontent.com/78312050/123228543-17c25b00-d508-11eb-85fd-d3ca3396b6a8.jpg)

# Data pre-processing
## Data engineering
- Data needs to be in numbers for the Machine to read, these numbers shoud also make sense in the real world. 
### Example of features with data set errors
#### animalage
- Dataset column is riddled with:
   - **strings** where days, weeks & months need to be converted into years
      - *Regular expression* usage to achieve this
   - **outlier errors** which need to make sense. Data that is on extreme ends can affect certain ML models 
      - *better to keep the data's SD relatively low*
      - Here i chose to replace the outlier age (100 year old cats/ dogs) with the googled average maximum age of a cat/dog
![regular expression](https://user-images.githubusercontent.com/78312050/124397544-f7ce3b00-dd42-11eb-8568-a1306e6e95d2.PNG)
### Before and after data-preprocessing
![age product](https://user-images.githubusercontent.com/78312050/124398208-1afae980-dd47-11eb-8f74-2de304e5754d.PNG)
## ML models used
Utilizing various Machine learning algorithmns and libraries to get the best model 
![Decision-Trees-Root-Node](https://user-images.githubusercontent.com/78312050/123955411-27481500-d9dc-11eb-91a8-321f66414e67.png)
![images (1)](https://user-images.githubusercontent.com/78312050/123228726-44767280-d508-11eb-91d5-7b23c811a19c.png)
![1523957272561](https://user-images.githubusercontent.com/78312050/123955599-637b7580-d9dc-11eb-9368-b50355d5b7fb.jpg)


