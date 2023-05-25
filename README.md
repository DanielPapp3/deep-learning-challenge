# deep-learning-challenge

## Purpose of the Analysis:
Utilize knowledge of deep learning models to create a tool to assist the nonprofit foundation Alphabet Soup in selecting the applicants for funding with the best chance of success in their ventures. The goal is to create a model that can successfully predict successful ventures with at least 75% accuracy.

## Answers to Data Preprocessing Questions:
* __Target Variable(s):__ The target variable is the "IS_SUCCESSFUL" variable.

* __Feature Variable(s):__
* APPLICATION_TYPE
* AFFILIATION
* CLASSIFICATION
* USE_CASE
* ORGANIZATION
* STATUS
* INCOME_AMT
* SPECIAL_CONSIDERATION
* ASK_AMT
* NAME (In Optimization Model only)

* __Removed Feature(s):__
* EIN
* NAME (In base model. Added it back into optimized model)

## Answers to Compiling, Training, and Evaluation Questions:
Both the original and optimized model encompassed three hidden layers. The original model comprised of 80, 30, and 1 neurons in those layers, respectively, and employed rectified linear unit (ReLU) activation functions. The optimized model used 14, 7, and 1 neurons for its layers in conjunction with the ReLU activation function. 

Below is the structure for the original model:

![Original Model Neuron Structure](https://github.com/DanielPapp3/deep-learning-challenge/assets/119254860/4047c331-7d42-44cd-853c-497f46292b32)

Below is the structure for the optimized model:

![Optimized Model Structure](https://github.com/DanielPapp3/deep-learning-challenge/assets/119254860/d6cd6e60-e89a-4372-b4ad-197634911ad7)

For binary classification purposes, the output layer employs a sigmoid activation function. This structural configuration was chosen to strike a balance between the ability for the model to pick up on the patterns in the data wihtout running too large of a risk of overfitting.

As shown below, the original model was unable to achieve the target model performance.

![Original Model Accuracy](https://github.com/DanielPapp3/deep-learning-challenge/assets/119254860/28b70c96-0815-4339-8089-2d769db09a3c)

However, after adjusting the Feature Variables (adding Name back in and filtering out those names that appeared less than 5 times), tweaking the cutoff values for classifications (down to 100 from 800), and adjusting the models hidden layers (described above) and epochs (down to 20 from 100) the optimized model was able to achieve an accuracy of 79.02% as shown below:

![Optimized Model Accuracy](https://github.com/DanielPapp3/deep-learning-challenge/assets/119254860/1c4c58ff-ba6f-4a5a-96eb-3fcf5b1640c5)

## Summary
Following multiple optimizations to the data preprocessing and neural structure it proved possible to enhance the model's efficacy to a satisfactory level which allowed it to attain an accuracy above the goal at 79.02%.

In terms of a viable alternative approach, there are a few solid options. Most notably, the utilization of either a Random Forest Classifier or a Gradient Boosting Classifier as these ensemble learning methods possess inherent capabilities that could make them an even more viable option in terms of accuracy and generalization, while mitigating some of the susceptibility to overfitting that can occur when using deep learning models.
