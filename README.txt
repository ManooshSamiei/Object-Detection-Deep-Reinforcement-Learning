COMP 767 Final Project by Manoosh Samiei and Ruofeng Li (2020/04/20)
---------------------------------------------------------------------------------

In MEGA:

- We stored all our experiments in this MEGA cloud drive, including all the notebooks we used to train and test the models, as well as the best pre-trained model for each experiment.

- You can find all the related documents of an experiment in the corresponding directory. 

For example, for the batch size experiment of hierarchical model, you should go to Hierarchical Model - experiments(with aeroplane class) - Changing Batch Size for training DQN. 

- In each experiment folder, you should be able to find sub-directories containing all tested values for that hyperparameter. 

For example, in the Changing Batch Size for traning DQN folder, you can find the Batch size = 50 and the Batch size = 200 folders

- The notebooks contain all the visualizations of testing results corresponding to the experiments.

-Use the more intructions on how to test/train models for hierarchical/dynamic approach.
---------------------------------------------------------------------------------
Kaggle.json key file
---------------------------------------------------------------------------------

Since the number of files in folders of VOC 2012 dataset is very large, mounting this dataset from google drive crashes the google colab sessions. Thus, we download dataset directly from Kaggle website when we run the code. 

To download dataset from kaggle, you need a kaggle.json key. We provided this key file in the code base. If you like to download your own kaggle key from your account, use below instructions:

- Go to the Kaggle website (www.kaggle.com)

- Register for a Kaggle account (log in to the exsiting account if you already have one)

- Go to "My Account"

- Select "Create New API Token" under the API section to download the kaggle.json file

---------------------------------------------------------------------------------
Hierarchical Method
---------------------------------------------------------------------------------
To test models:

-upload the corresponding notebook to google Colab

-connect to google colab GPU

-upload the model to the left folder bar of google colab in the following directory:
--pascal/models_image_zooms
--to manually upload a file in folder, right click on the folder and click upload
--Be careful that the name of the model used in the testing part should be changed to the name of the model (if it is not the same as the uploaded model). 

-Upload kaggle json file, using code snippet, to download dataset directly
-run code snippets in the order they are placed, except mounting google drive and training agent code
-run testing agent part
---------------------------------------------------------------------------------
To train models:

-connect to google colab GPU
-Upload kaggle json file, using code snippet, to download dataset directly
-run code snippets in the order they are placed
-Mount your google drive to save trained model for each spoch
-run training agent part
-The models will be also saved in colab folder tab, and can be downloaded manually.

---------------------------------------------------------------------------------

**For each experiment, several parameters were changed in code
Thus we included the notebook file and the best trained model for easier reproducibility.
**We have generated the output of all experiments in notebooks.

---------------------------------------------------------------------------------
Dynamic method
---------------------------------------------------------------------------------

-connect to google colab GPU

-upload model to the left folder bar of google colab in pascal folder
--to manually upload a file in folder, right click on the folder and click upload

-Upload kaggle json file, using code snippet, to download dataset directly
-run code snippets in the order they are placed

**in some notebooks, the directory of loading model, in test function, might have been changed to google drive directory. To make it compatible with manual upload of models, simply comment out those lines.

To only test a model, you need to comments out calling train_deep_q() function in main function, and directly run the test.

**We have generated the output of all notebooks for different object classes.
---------------------------------------------------------------------------------
** Note: It is highly recommended to run the code with GPU since the runtime is around 30mins per epoch for the hierarchical model and around 1hour per epoch for the dynamic model.

.................................................................................
Test, train split:
 
In training, we use images listed in objectclass_train.txt file in datatset. For testing we use images listed in objectclass_val.txt file in datatset. 


Number of examples for different object categories do not differ significantly. For most classes, there are around 300 images for each class. However, among classes we tested, 'car' class has around 500 images. 

Table of results are included in our submitted report.

In this project, we used google colaboratoru gpu to train and test our models.
