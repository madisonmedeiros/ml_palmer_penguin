# Penguin Health Prediction

## Project Overview

This project utilizes machine learning models to predict the health status of penguins based on various physical and environmental attributes. The goal is to demonstrate how different machine-learning techniques can be applied to a biological dataset to infer health conditions. This project is for educational use and intended to help students and enthusiasts understand the application of machine learning in biological sciences.

## Models Used

	•	Logistic Regression: Used for establishing a baseline for binary classification tasks.
	•	Decision Tree: Offers good interpretability and helps understand feature importance.
	•	K-Nearest Neighbors (KNN): Explores the impact of instance-based learning where predictions are based on neighborhood similarity.

## Dataset: 

Source: https://www.kaggle.com/datasets/samybaladram/palmers-penguin-dataset-extended?resource=download

The dataset includes attributes such as species, island, sex, diet, year of data collection, life stage, body mass, bill length, bill depth, flipper length, and health metrics of penguins. The specific details of the dataset sources and attributes are outlined below:

Attributes:
	•	Species: Species of the penguin (e.g., Adelie, Chinstrap, Gentoo)
	•	Island: The island where the penguin was found (e.g., Biscoe, Dream, Torgensen)
	•	Sex: Gender of the penguin (Male, Female)
	•	Diet: Primary diet of the penguin (Fish, Krill, Squid)
	•	Year: Year the data was collected (2021-2025)
	•	Life Stage: The life stage of the penguin (Chick, Juvenile, Adult)
	•	Body Mass (g): Body mass in grams
	•	Bill Length (mm): Bill length in millimeters
	•	Bill Depth (mm): Bill depth in millimeters
	•	Flipper Length (mm): Flipper length in millimeters
	•	Health Metrics: Health status of the penguin (Healthy, Overweight, Underweight)

 ## Results

 ![image](https://github.com/madisonmedeiros/ml_palmer_penguin/assets/117107317/a3f53990-cd9a-48e0-93dd-0c40414a53d2)
 The decision tree model had the highest accuracy compared to logistic regression and k-nearest neighbor. Cross-validation was performed to evaluate the model's accuracy further; the Decision Tree model shows a very high average accuracy of 0.93 with very low variability in accuracy scores across different folds (±0.02). This indicates that the Decision Tree model is highly effective and stable across different subsets of the data. The high accuracy suggests that the Decision Tree model can capture complex patterns in the data. However, the consistently high performance might also signal to investigate if the model is overfitting, especially since Decision Trees are prone to this.

 Logistic Regression has a much lower average accuracy of 0.66 and a variability of ±0.03. Moderate accuracy suggests that logistic regression, which models relationships linearly, might struggle with the complexities or non-linearities in the dataset. The low variance in the accuracy indicates that the model’s performance is stable across different subsets, but it does not capture the underlying patterns as effectively as the Decision Tree.

KNN's accuracy is similar to Logistic Regression's at 0.63, with a variability of ±0.03. This performance suggests that this model may also be limited in handling the complexity of the data or that the hyperparameters (like the number of neighbors) are not optimally tuned. KNN’s performance can be particularly sensitive to the scale of the data and the choice of distance metric, implying that feature scaling or different parameter settings might be needed to improve its efficacy.

![image](https://github.com/madisonmedeiros/ml_palmer_penguin/assets/117107317/3120d848-9faa-49f6-a70c-144188ef65f5)
The model heavily relies on physical measurements (body_mass_g, bill_length_mm, and flipper_length_mm) and species type. This suggests that physiological characteristics and species are key determinants of the target variable in this dataset. The importance of species-specific features implies that different penguin species may have distinct health profiles or conditions, which are significant in predicting outcomes.
The relatively low importance of features like year and island locations suggests that temporal and certain geographical variables may be less critical in influencing the health metrics, at least within the scope of this model and dataset.

![image](https://github.com/madisonmedeiros/ml_palmer_penguin/assets/117107317/31943f6c-e570-4241-9c4d-b679f28bd964)
The pruned tree focuses on the most impactful features, as shown:
	•	Body Mass (body_mass_g): Continues to be the dominant feature, reinforcing its significance in determining health status.
	•	Diet (diet_fish) and Species: These features appear in the subsequent splits, indicating their roles are also essential but secondary to body mass.
	•	Leaf Nodes: The pruned tree has fewer leaf nodes, each representing a more significant number of samples, which simplifies the decision-making process. This reduction in complexity suggests a model that balances detail with broad applicability. 
However, pruning the tree that much came at the cost of accuracy, so it was further investigated what would be the most viable and efficient depth, which was chosen to be 13. and a max number of leaves at 4


