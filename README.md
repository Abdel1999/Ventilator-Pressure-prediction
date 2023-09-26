# Ventilator_Pressure_prediction

## **Dataset description** :

The ventilator data used in this competition was produced using a modified open-source ventilator connected to an artificial bellows test lung via a respiratory circuit. The diagram below illustrates the setup, with the two control inputs highlighted in green and the state variable (airway pressure) to predict in blue. The first control input is a continuous variable from 0 to 100 representing the percentage the inspiratory solenoid valve is open to let air into the lung (i.e., 0 is completely closed and no air is let in and 100 is completely open). The second control input is a binary variable representing whether the exploratory valve is open (1) or closed (0) to let air out.

<div align='center'><img width="488" alt="dataset_exp" src="https://github.com/Abdel1999/Ventlator_Pressure_prediction/assets/123161748/1240dd44-7261-44e3-8426-a330341ebe25">
</div>

**Dataset features :**

- id :globally-unique time step identifier across an entire file
breath_id - globally-unique time step for breaths
- R :lung attribute indicating how restricted the airway is (in cmH2O/L/S). Physically, this is the change in pressure per change in flow (air volume per time). Intuitively, one can imagine blowing up a balloon through a straw. We can change R by changing the diameter of the straw, with higher R being harder to blow.
- C :lung attribute indicating how compliant the lung is (in mL/cmH2O). Physically, this is the change in volume per change in pressure. Intuitively, one can imagine the same balloon example. We can change C by changing the thickness of the balloon’s latex, with higher C having thinner latex and easier to blow.
- time_step :the actual time stamp.
- u_in :the control input for the inspiratory solenoid valve. Ranges from 0 to 100.
- u_out :the control input for the exploratory solenoid valve. Either 0 or 1.
- pressure :the airway pressure measured in the respiratory circuit, measured in cmH2O.

**Project description :**

What do doctors do when a patient has trouble breathing? They use a ventilator to pump oxygen into a sedated patient's lungs via a tube in the windpipe. But mechanical ventilation is a clinician-intensive procedure, a limitation that was prominently on display during the early days of the COVID-19 pandemic. At the same time, developing new methods for controlling mechanical ventilators is prohibitively expensive, even before reaching clinical trials. High-quality simulators could reduce this barrier.

Current simulators are trained as an ensemble, where each model simulates a single lung setting. However, lungs and their attributes form a continuous space, so a parametric approach must be explored that would consider the differences in patient lungs.

Partnering with Princeton University, the team at Google Brain aims to grow the community around machine learning for mechanical ventilation control. They believe that neural networks and deep learning can better generalize across lungs with varying characteristics than the current industry standard of PID controllers.

**Prerequisites :**
- python/jupyter noyebook
- pip 

**package installing :**

```bash
pip install pandas
pip install scikit-learn
pip install seaborn
pip install matplotlib
pip install numpy
pip install tensorflow
```

**Methodology :**

The aim of the project is to predict airway pressure using AI algorithms. To achieve this, I adopted the following steps:
- Performing data exploration and analysis of the main features, including measuring correlations between features and examining their distributions.
- Conducting feature engineering on the provided original features.
- Preprocessing the data to handle missing and infinite values.
- Splitting the dataset into training, validation, and test sets (the validation set is used for model selection and hyperparameter tuning).
- Comparing two different machine learning algorithms, namely Linear Regression and Artificial Neural Networks (ANN), to determine which one provides better predictions.
- Evaluating the models using the Mean Absolute Error (MAE) evaluation metric with R**2 in both used algorithms.
- Choosing ANN as the best algorithm for predicting pressure values in the test set.
