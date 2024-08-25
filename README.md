# Intrusion Detection System (CMPE279)
## Background Information
Intrusion detection system project for the Software Security Technologies (CMPE-279) Masters course offered at SJSU.<br>
This project serves as an introduction to the importance of datasets for IDS systems and the performance of different training models.<br>
The goal for this project is to train a model to accurately detect malicious packets using selected network features. 

## Tools Used
Languages: Python<br>
Tools: Jupyter Notebook<br>

## Process

### Data Exploration & Preprocessing
NSL-KDD is dataset that was chosen for this project. This dataset was published in 2009 and was created to help benchmark and verify
different intrusion detection systems. This dataset is an improved rendition based on the earlier version (KDD 99). Some improvements would include
a more balanced selection of records between different difficulty levels, a reasonable amount of records within each dataset, removed redundant records
in the training dataset, and removed duplicate records in the testing dataset.

For preprocessing, the data was labeled with column names and the correctness of the dataset was verified. One verification step that was done was to 
check for any columns with empty values. During this stage, graphs were created to help visualize the contents of the test data. 
The following images are some of the visuals created to help determine the frequency and type of the attacks contained within the dataset.
![image](https://github.com/user-attachments/assets/143680fb-c3f4-4293-bab2-a91e539e11c0)
![image](https://github.com/user-attachments/assets/860d2a3d-83e1-4dfc-9c7e-f6660cb34367)

### Feature Encoding
The data was split into features for training/testing (x_train, x_test), and labels for training/testing (y_train, y_test). Once the data was split,
it was then sorted and aligned correctly with the labels. The next step was to explore different encoding methods. Since training models work with numerical values, 
encoding was required to convert labels and strings into a numerical input data. The two encoding methods that were used include one hot encoding (OHE) and ordinal encoding (OE).
One hot encoding created binary vectors where each index contains a binary value (0 or 1), while ordinal encoding assigns integer values to each unique category. We decided to 
explore both encoding methods as a learning opportunity and to check for any discrepancies based on the chosen encoding model.

Example of OHE output (using flags):
![image](https://github.com/user-attachments/assets/f0f11e46-b245-4958-9106-5caf7eb3c4f7) 

Example of OE output (using numeric labels): <br>
![image](https://github.com/user-attachments/assets/c4c96a61-26c8-4257-ba8a-793cfcb32328)

### Feature Selection + Modeling
For selected features, SelectKBest function was used from the scikit-learn library. This was done as a way to get a rough idea on what features might be useful to analyze. The following
are the top 10 features that were selected:<br>
![image](https://github.com/user-attachments/assets/ce419f1d-6a16-41c0-866c-a80d514b249c)

As for modeling, the Random Forest, Neural Network, and Logistic Regression algorithms were used. The runtime for each algorithm was tracked, in addition to the accuracy, precision, recall,
and F-1 score calculations. These metrics were calculated using the true negative, true positive, false negative, and false positive values obtained from the generated confusion matrix. This process was done 
for each algorithm (using all features and selected features), and later compared to each other.
Example of how the metrics were generated:<br>
![image](https://github.com/user-attachments/assets/53d6c3d5-05e7-427f-b2bb-f4b31ee250a1)

Performance comparisons for each training model:
![image](https://github.com/user-attachments/assets/d7457807-3de9-4347-bc69-e1065ea8ffdc)
![image](https://github.com/user-attachments/assets/3279f5ca-5bc2-48f3-801a-fe5c0e9368f5)

Note: The full analysis and results are available on the uploaded Jupyter Notebook
