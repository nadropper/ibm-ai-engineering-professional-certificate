# Data Scientist vs AI Engineer: Understanding the Key Differences

*From the IBM AI Engineering Professional Certificate course*

## Introduction

For many years, data science has been called "the sexiest job of the 21st 
century." However, in recent years, there's a new job vying for that title: 
the AI Engineer role. Who are these new professionals? Are they just data 
scientists in disguise?

To answer these questions, I'll outline four key areas
where the work of a Data Scientist differs from an AI Engineer,
specifically a Generative AI Engineer.

## The Changing Landscape

Before diving into the differences, we need to understand what's happening 
in the industry. Traditionally, data scientists have always used AI models 
for their analysis. So what's changed?

With the advent of Generative AI, the boundaries of what AI can do are being 
pushed in unprecedented ways. These breakthroughs have been so groundbreaking 
that Generative AI has split off into its own distinct field, which we call 
AI Engineering.

## Four Key Differences

### 1. Use Cases: Storyteller vs System Builder

At a high level, think of a Data Scientist as a *data storyteller*. They 
take massive amounts of messy real-world data and use mathematical models to 
translate this data into insights.

On the other hand, think of an AI Engineer as an *AI system builder*. They 
use foundation models to build Generative AI systems that help transform 
business processes.

#### Data Science Use Cases

**Descriptive Analytics (Describing the Past):**
- **Exploratory Data Analysis (EDA)**: Graphing data and performing 
  statistical inference
- **Clustering**: Grouping similar data points based on characteristics, 
  such as customer segmentation

**Predictive Analytics (Predicting the Future):**
- **Regression Models**: Predicting numeric values like temperature or revenue
- **Classification Models**: Predicting categorical values like success or 
  failure

#### AI Engineering Use Cases

**Prescriptive Use Cases (Choosing the Best Action):**
- **Decision Optimization**: Assessing possible actions and choosing the most 
  optimal path based on requirements or standards
- **Recommendation Engines**: Suggesting targeted marketing campaigns for 
  select customer bases

**Generative Use Cases:**
- **Intelligent Assistants**: Coding assistants or digital advisors
- **Chatbots**: Enabling conversational search through information retrieval 
  and content summarization

### 2. Data: The New Oil

People say data is the new oil because, like oil, you have to search for and 
find the right data, then use the right processes to transform it into 
various products that power different processes.

#### Data Scientists: Structured Data Focus

For data scientists, the oil of choice is often **structured data** (tabular 
data). While data scientists still work with unstructured data, they don't 
use it as much as AI engineers.

**Characteristics:**
- Tables with hundreds to hundreds of thousands of observations
- Requires extensive cleaning and preprocessing before modeling
- Cleaning involves removing outliers, joining and filtering tables, or 
  creating new features
- Clean data is used to train various machine learning models

#### AI Engineers: Unstructured Data Focus

For AI engineers, the oil of choice is mainly **unstructured data** such as 
text, images, videos, and audio files.

**Example - Large Language Models (LLMs):**
- Require billions to trillions of tokens of text for training
- Much larger scale compared to traditional machine learning models

### 3. Models: Narrow vs Wide Scope

#### Data Science Models

The data science toolbox consists of hundreds of different models and 
algorithms to choose from.

**Characteristics:**
- Each use case requires gathering a different dataset and training a 
  different model
- **Narrow scope**: Harder to generalize beyond the domain of training data
- Smaller in size (fewer parameters)
- Less compute power required for training and inference
- Faster training time (seconds to hours)

#### AI Engineering Models: Foundation Models

The Generative AI toolbox is less cluttered and really only contains one type 
of model: the **foundation model**.

**Revolutionary Characteristics:**
- Allow one single type of model to generalize to a wide range of tasks 
  without retraining
- **Wide scope**: Can generalize across multiple domains
- Much larger in size (billions of parameters)
- Require significantly more compute power (hundreds to thousands of GPUs)
- Longer training time (weeks to months)

### 4. Processes: Traditional ML vs AI Democratization

#### Traditional Data Science Process

1. **Use Case Identification**
2. **Data Selection** based on the use case
3. **Data Preparation**
4. **Model Training and Validation** using techniques such as:
   - Feature engineering
   - Cross-validation
   - Hyperparameter tuning
5. **Model Deployment** at an endpoint (e.g., in the cloud) for real-time 
   prediction and inference

#### Generative AI Process

1. **Use Case Identification**
2. **Skip directly to working with pre-trained models**

This is possible due to **AI democratization** - making AI more widely 
accessible to everyday users. The best foundation models are published to 
open-source communities like Hugging Face, and their generalizability and 
power out of the box make it easy for developers to get started.

**Key Techniques:**
- **Prompt Engineering**: Interacting with foundation models via natural 
  language instructions
- **Framework Integration**: Building larger AI systems using:
  - Chaining different prompts together
  - Parameter-Efficient Fine-Tuning (PEFT) on domain-specific data
  - Retrieval-Augmented Generation (RAG) to ground answers in truth
  - Autonomous agents for complex multi-step problem reasoning

**Final Step**: Embed the AI in a larger system or workflow through:
- Creating assistants or virtual agents
- Building larger applications with user interfaces
- Implementing automation solutions

## Summary: The Big Picture

The breakthroughs in Generative AI underpin many of the differences in use 
cases, data, models, and processes that data scientists and AI Engineers 
work on.

**Important Note**: There is still overlap between the two fields. For 
example:
- Data Scientists may still work on prescriptive use cases
- AI Engineers may still work with structured data

Regardless of these differences, both fields continue to evolve at a blazing 
fast pace, with new research papers, models, and tools emerging every single 
day. With data, AI, and a creative mind, really anything is possible.

---

*This content is adapted from the IBM AI Engineering Professional Certificate 
course, presented by Isaac Key, former data scientist turned AI engineer at 
IBM.*
