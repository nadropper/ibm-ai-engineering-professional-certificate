# Graded Quiz: Introduction to Machine Learning

1. You are building a model to estimate the exact blood sugar level
  of diabetic patients based on age, weight, and lifestyle habits.
  Which machine learning techniques will help in this task?
- [x] Regression technique
- [ ] Classification technique 
- [ ] Clustering technique 
- [ ] Association technique

> The answer is **Regression technique** because the problem asks
to estimate the "exact blood sugar level" of diabetic patients.
Blood sugar level is a continuous numerical value
(like 120 mg/dL, 85 mg/dL, etc.), not a category or class.
>
> **Regression** is the ML technique used when you want to predict
continuous numerical values. It finds relationships between input features
(age, weight, lifestyle habits) and outputs a specific numeric prediction.
>
> The other options wouldn't work for this task:
> - **Classification** predicts categories/classes (like "high," "normal,"
  "low" blood sugar)
> - **Clustering** groups similar data points together without
  predicting specific values
> - **Association** finds relationships between variables
  but doesn't predict target values
>
> Since we need to predict an exact numerical blood sugar level, regression is the appropriate technique.

2. Which of the following correctly describes the ML model lifecycle workflow?
- [ ] Define problem → Prepare data → Deploy model
- [ ] Prepare model → Clean model → Visualize model → Report model
- [ ] Prepare data → Design UI → Train model→ Collect feedback
- [x] Define problem → Collect data → Prepare data → Develop and evaluate model → Deploy model

3. Thomas is removing missing values and formatting the date field in the
  extracted data. What do you call this phase in the ML lifecycle?
- [ ] Data evaluation
- [ ] Problem definition
- [x] Data preparation
- [ ] Data cleaning

4. You are handling a ML project and want to select appropriate tools
  for data processing, modeling, and visualization. Which group of tools
  is correctly matched to machine learning tasks?
- [ ] Hadoop, Tableau, and JavaScript 
- [ ] Excel, PowerPoint, and Illustrator
- [ ] Spark, Premiere Pro, and Notepad 
- [x] Pandas, Scikit-learn, and Matplotlib 

5. Twinkle wants to train and evaluate a ML model using Python and prefers
  a library with built-in support. Which of the following statements
  best describes the capabilities of a scikit-learn library?
- [ ] Scikit-learn works with unstructured video and audio data.
- [x] Scikit-learn preprocesses data, trains, evaluates, and exports data.
- [ ] Scikit-learn generates AI art and images before data preprocessing.
- [ ] Scikit-learn plots and graphs to gain data insights and visualization.

6. Which Python library is commonly used for data manipulation and analysis in ML? 
- [ ] NumPy 
- [x] Pandas 
- [ ] Matplotlib 
- [ ] Keras 

7. Pristin is training a ML model using Scikit-learn but notices inconsistent accuracy.
  She decides to adjust values like the number of neighbors in KNN
  and the regularization strength in logistic regression.
  What is the purpose of this step?
- [ ] To adjust the model’s internal parameters automatically 
- [ ] To scale the data 
- [x] To fine-tune the parameters that control the model’s behavior 
- [ ] To change the model’s architecture 

