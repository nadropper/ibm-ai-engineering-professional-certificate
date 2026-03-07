# Introduction to Machine Learning

This is module 1 of the [Machine Learning with Python](https://www.coursera.org/learn/machine-learning-with-python?specialization=ai-engineer) course.

In this module, I explored foundational machine learning concepts
that prepared me for hands-on modeling with Python.
I learned the relevance of Python and scikit-learn in machine learning,
summarized the IBM AI Engineering certification path,
and classified common types of learning algorithms.
I also outlined the stages of the machine learning model lifecycle
and described what a typical day looks like for a machine learning engineer.
I was also able to compare key roles in the AI field,
identify widely used open-source tools, and learn to utilize scikit-learn
to build and evaluate simple models.

## An Overview of Machine Learning

An extensive review of this topic can be found [here](/C1-Machine-Learning-with-Python/M1-Introduction-to-Machine-Learning/01-An-Overview-of-Machine-Learning.md).

Artificial intelligence, or AI, makes computers appear intelligent
by simulating the cognitive abilities of humans. AI is a general field
with a broad scope. It comprises computer vision, natural language processing,
generative AI, machine learning, and deep learning.

[IMG]

Machine learning, or ML, is the subset of AI that uses algorithms
and requires feature engineering by practitioners.
Deep learning distinguishes itself from traditional machine learning
by using many-layered neural networks that automatically extract features
from highly complex, unstructured big data.

[IMG]

### Machine Learning Paradigms

Machine learning teaches computers to learn from data, identify patterns,
and make decisions without receiving any explicit instructions
from a human being. ML algorithms use computational methods
to learn information directly from data without depending on any fixed algorithm.

Machine learning models differ in how they learn. For example,
__supervised learning__ models train on labeled data to learn
how to make inferences on new data, enabling them
to predict otherwise unknown labels. __Unsupervised learning__ works
_without_ labels by finding patterns in data. __Semi-supervised learning__
trains on a relatively small subset of data that is already labeled,
and _iteratively_ retrains itself by adding new labels that it generates
with reasonably high confidence. __Reinforcement learning__ simulates
an artificially intelligent agent interacting with its environment
and learns how to make decisions based on feedback from its environment.

[IMG]

### Machine Learning Techniques

Selecting a machine learning technique depends on several factors,
such as the problem you're trying to solve, the type of data you have,
the available resources, and the desired outcome. A __classification technique__
is used to predict the class or category of a case,
such as whether a cell is benign or malignant or whether a customer will churn.
The __regression/estimation technique__ is used to predict continuous values,
such as the price of a house based on its characteristics
or the CO2 emissions from a car's engine. __Clustering groups of similar cases__,
for example, can find similar patients or can be used for customer segmentation
in the banking field. The __association technique__ is used to find items
or events that often co-occur, such as grocery items usually bought together
by a particular customer or market segment. __Anomaly detection__ is used
to discover abnormal and unusual cases. For example,
it's used for credit card fraud detection. __Sequence mining__ is used
to predict the next event. For instance, the clickstream analytics in websites.
__Dimension reduction__ is used to reduce data size,
particularly the number of features needed. And finally, __recommendation systems__,
which associate people's preferences with others who have similar tastes
and recommends new items to them, such as books or movies.

#### Classification and Regression

To train your machine learning model on supervised data,
you can select between the classification or regression technique.

Classification categorizes input data into one of several predefined categories
or classes, and then makes predictions about the class membership
of new observations.

Regression is different from classification. It does not make predictions
about the class membership of new input data. Regression predicts
continuous numerical values from input data.

[IMG]

#### Clustering

Clustering is one of many unsupervised machine learning techniques
for data modeling. It's used to group data points or objects
that are somehow similar. For example, in this chart,
we use a clustering algorithm to represent data points in green, red,
and blue color.

[IMG]

The uncategorized data points represented in black color are considered noise.

### Applications of Machine Learning

This is a human cell sample extracted from a patient.
It has some unique characteristics. For example, its clump thickness is 6,
its uniformity of cell size is 1, its marginal adhesion is 1, and so on.
An interesting question we can ask by looking at this chart is,
is this a benign or malignant cell? Compared to a benign cell,
a malignant cell invades its surrounding tissue and spreads around the body.

Identifying the cell type early can be the key to the patient's survival.
One could easily presume that only a doctor with years of experience could identify
the cell and confirm if the patient is developing a cancer or not.

Imagine you've obtained a dataset containing characteristics of thousands
of human cell samples extracted from patients believed to be at risk
of developing cancer. Analysis of the original data showed that many
of the characteristics differed significantly between benign
and malignant samples. You can use the values of these cell characteristics
in samples from other patients to indicate whether a new sample might be benign
or malignant. You should clean your data, select a proper algorithm
for building a prediction model, and train your model to understand patterns
of benign or malignant cells within the data. Once the model has been trained
by going through data iteratively, it can be used to predict your new
or unknown cell with a rather high accuracy. This is the power
of machine learning.

Machine learning impacts society in a very meaningful way. How do Amazon
and Netflix recommend content and products for their users?
They use machine learning. This is similar to how your friends might recommend
a television show to you based on their knowledge of the types
of shows you like to watch. How do you think banks make a decision
when approving a loan application? They use machine learning to predict
each applicant's default probability and then augment their decision
to approve or deny the loan application based on that probability. 
How do telecommunication companies find how many of their customers will churn?
They use demographic data to segment their customers and predict whether
a customer will unsubscribe within the next month.

2. [Machine Learning Model Lifecycle](/C1-Machine-Learning-with-Python/M1-Introduction-to-Machine-Learning/01-An-Overview-of-Machine-Learning.md)
3. [A Day in the life of a Machine Learning Engineer](/C1-Machine-Learning-with-Python/M1-Introduction-to-Machine-Learning/03-A-Day-in-the-Life-of-a-ML-Engineer.md)
4. [Data Scientist vs AI Engineer](/C1-Machine-Learning-with-Python/M1-Introduction-to-Machine-Learning/04-Data-Scientist-vs-AI-Engineer.md)
5. Tools for Machine Learning
6. Scikit-learn Machine Learning Ecosystem

## Module 1 Summary and Highlights

- Artificial intelligence (AI) simulates human cognition,
  while machine learning (ML) uses algorithms and requires feature engineering
  to learn from data.
- Machine learning includes different types of models: supervised learning,
  which uses labeled data to make predictions; unsupervised learning,
  which finds patterns in unlabeled data; and semi-supervised learning,
  which trains on a small subset of labeled data.
- Key factors for choosing a machine learning technique include the type
  of problem to be solved, the available data, available resources,
  and the desired outcome.
- Machine learning techniques include anomaly detection for identifying
  unusual cases like fraud, classification for categorizing new data,
  regression for predicting continuous values, and clustering for grouping
  similar data points without labels.
- Machine learning tools support pipelines with modules for data preprocessing,
  model building, evaluation, optimization, and deployment.
- R is commonly used in machine learning for statistical analysis
  and data exploration, while Python offers a vast array of libraries
  for different machine learning tasks. Other programming languages used in ML
  include Julia, Scala, Java, and JavaScript, each suited to specific
  applications like high-performance computing and web-based ML models.
- Data visualization tools such as Matplotlib and Seaborn create
  customizable plots, ggplot2 enables building graphics in layers,
  and Tableau provides interactive data dashboards.
- Python libraries commonly used in machine learning include NumPy
  for numerical computations, Pandas for data analysis and preparation,
  SciPy for scientific computing, and Scikit-learn for building traditional
  machine learning models.
- Deep learning frameworks such as TensorFlow, Keras, Theano, and PyTorch
  support the design, training, and testing of neural networks used in areas
  like computer vision and natural language processing.
- Computer vision tools enable applications like object detection,
  image classification, and facial recognition, while natural language
  processing (NLP) tools like NLTK, TextBlob, and Stanza facilitate text
  processing, sentiment analysis, and language parsing.
- Generative AI tools use artificial intelligence to create new content,
  including text, images, music, and other media, based on input data
  or prompts.
- Scikit-learn provides a range of functions, including classification,
  regression, clustering, data preprocessing, model evaluation,
  and exporting models for production use.
- The ML ecosystem includes a network of tools, frameworks, libraries,
  platforms, and processes that collectively support the development
  and management of machine learning models.

## Assignments

1. [Practice Quiz: Introduction to Machine Learning](/C1-Machine-Learning-with-Python/M1-Introduction-to-Machine-Learning/Quizzes/Practice-Quiz-Intro-to-ML.md)
2. [Graded Quiz: Introduction to Machine Learning](/C1-Machine-Learning-with-Python/M1-Introduction-to-Machine-Learning/Quizzes/Graded-Quiz-Intro-to-ML.md)
