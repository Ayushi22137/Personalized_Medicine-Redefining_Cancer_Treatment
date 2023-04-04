# Personalized_Medicine-Redefining_Cancer_Treatment
Determining the class of cancer-causing mutations using text and genetic data

## Source

https://www.kaggle.com/c/msk-redefining-cancer-treatment

## Inspiration
* A cancer tumor can have thousands of genetic mutations. But the challenge is distinguishing the mutations that contribute to tumor growth (drivers) from the neutral mutations (passengers).
* A lot has been said during the past several years about precision medicine and, more important, how genetic testing would disrupt the way diseases like cancer are treated. Once sequenced, a cancer tumor can have thousands of genetic mutations.
* Currently interpretation of genetic mutations is done manually. This is a very time-consuming task where a clinical pathologist has to manually review and classify every single genetic mutation based on evidence from text-based clinical literature.
* MSKCC is an institution which made available an expert-annotated knowledge base where world-class researchers and oncologists have manually annotated thousands of mutations.
* We developed a ML model which can perform this task of classifying the genetic mutations in different categories using text from clinical literature and gene-variation data.


## Basic Description about Cancer and the Genes

Genes are in the DNA of each cell in your body. They control how the cell functions, including:

* How quickly it grows
* How often it divides
* How long it lives

Genes control how your cells work by making proteins. The proteins have specific functions and act as messengers for the cell.Each gene must have the correct instructions for making its protein. This allows the protein to perform the correct function for the cell.All cancers begin when one or more genes in a cell mutate. A mutation is a change. It creates an abnormal protein. Or it may prevent a protein’s formation. An abnormal protein provides different information than a normal protein. This can cause cells to multiply uncontrollably and become cancerous. Mutations happen often. A mutation may be beneficial, harmful, or neutral. This depends where in the gene the change occurs. Typically, the body corrects most mutations. A single mutation will likely not cause cancer. Usually, cancer occurs from multiple mutations over a lifetime. That is why cancer occurs more often in older people. They have had more opportunities for mutations to build up.

## Abstract
Our project evaluates the process of text and genetic data-based machine learning modeling for classification. The data sets consist of descriptions of genetic mutations, in which each data point is represented by an associated gene, corresponding variations, and text-based excerpts from clinical literature. This data was published by Memorial Sloan Kettering Cancer Center (MSKCC). Text data is encoded with the help of the TF-IDF method and genetic data have been featurized using one-hot encoding. Further, the data modeling is performed using different classification algorithms to find out the best-performing model. The hyperparameters are fine tuned to get the best possible results. The most excellent accuracy score is observed using the Histogram Gradient Boosting algorithm. 

Both, training, and test data sets are provided via two different files. One (training/test_variants) provides the information about the genetic mutations, on other hand (training/test_text) provides the clinical evidence (text) that our human experts used to classify the genetic mutations. Both are linked via 
the ID field. 


## Workflow: EDA, Data Cleaning and Featurization
1. Found 5 NANs which were replaced manually from standard literature reports.
2. Class Imbalanced was observed, which was delath post featurization.
3. Text preprocessing: Lowering, Punctuation removal, stopword removal, stemming.
4. TF-IDF featurization with max features = 700.
5. Dimensionality reduction using PCA conserving 95% variance.
6. One Hot Encoding of gene and variation information.
7. Stacking of text features and gene-variation features.
8. Removal of data imbalance using SMOTE.

## Modelling Results
For model selection we checked the performance of 15 models with default parameters.
Finally, we tuned and trained five models:
1. Logistic Regression
2. SVM
3. Random Forest
4. Bagging with RF
5. Histogram Gradient Boosting

## Conclusion
Histogram Gradient Boosting Classifier worked best for our data with test log-loss and train log-loss
to be 0.429 and 0.147, respectively. Grid Search is used to generate the optimum hyperparameters
for the model, which were l2 regularization = 0, max depth = 6, max-leaf nodes = 31

## Future Scope
The proposed model can be enhanced by incorporating other text transformation
models like truncated singular value decomposition (SVD) and Doc2Vec for text conversion. Along
with this, different machine learning classifiers like Multinomial Naïve Bayes and Deep Learning
classifiers (RNN, LSTM, Conv1D, and Gated Recurrent Units) can be applied to the sparse matrix,
which can lead to an increase in the model efficiency. Also, similar gene mutation and classification
techniques can be extended to find a cure for diseases other than Cancer and can be a breakthrough
technology in personalized medical space.




