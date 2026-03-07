# A Day in the Life of a Machine Learning Engineer

*From the IBM AI Engineering Professional Certificate course*

## Learning Objectives

After watching this video, you will be able to:
- Describe the importance and requirements of each process in the lifecycle 
  of a machine learning model
- Name the processes that are more time-consuming than others

## Project Context: Product Recommendation System

To demonstrate the machine learning model lifecycle, let's explore a current 
project focused on increasing business revenue through a product recommendation 
system for beauty products.

### Problem Definition

The first step involves working with the client to define the end-user's pain 
point:

**User Story**: "As a beauty product customer, I would like to receive 
recommendations for other products based on my purchase history so that I 
will be able to address my skincare needs and improve the overall health of 
my skin."

Defining the problem or stating the situation is crucial because it ensures 
the machine learning solution aligns with the client's actual needs.

## The Machine Learning Model Lifecycle

### 1. Data Collection

Once we understand the client's needs, the next step is data collection. This 
involves determining what kind of data the company has and identifying its 
sources.

**Types of Data Needed:**

**User Data:**
- Demographics
- Purchase history
- Transaction details
- Saved products
- Liked products
- Search history
- Most visited products

**Product Data:**
- Inventory of products
- Product functionality
- Ingredients
- Popularity metrics
- Customer ratings

**Data Integration:**
The collected data undergoes major transformation through wrangling, 
aggregating, joining, merging, and mapping onto one central source. This 
reduces the need to deal with multiple databases every time we need to pull 
data.

### 2. Data Preparation

Most data from multiple sources contains errors, different formatting, and 
missing values. This process often overlaps with data collection as they can 
be done simultaneously.

**Key Focus Areas:**

**Data Cleaning:**
- Filter out irrelevant data
- Remove extreme values to avoid dataset influence
- Handle missing values (remove or randomly generate based on context)
- Ensure proper formatting (dates in date format, strings properly identified)

**Feature Engineering:**
- Calculate average duration between transactions for each user
- Identify which products users buy most frequently
- Create features identifying skin issues each product targets
- Assign product characteristics to users

**Exploratory Data Analysis:**
- Create plots to visually identify patterns
- Validate data based on subject matter expert input
- Perform correlation analysis to identify important variables affecting 
  buying habits and needs
- Determine data splitting strategy (random split vs. chronological split)

For this project, the most recent transactions were placed in the test set, 
ensuring at least one transaction per user remained in the training set.

### 3. Model Development

In this step, we build the machine learning model. The approach focuses on 
leveraging existing frameworks and resources rather than creating solutions 
from scratch.

**Technique 1: Content-Based Filtering**
This technique finds similarity between products based on product content.

**Example Logic:** If someone uses a cleanser with high water content, they 
likely have dry skin and would benefit from a highly moisturizing product.

**Process:**
- Create similarity scores for products a user has purchased
- Rank them against other products
- Recommend the most similar products
- Consider additional factors (e.g., ingredients the user avoids)

**Technique 2: Collaborative Filtering**
This technique uses user data to create similarities between users based on 
how they view products.

**Process:**
- Group users based on characteristics (age, region, skin type, rated/purchased 
  products)
- Calculate average ratings for existing group members
- Assume new users will rate similarly to their group average
- Recommend products based on high group ratings

**Final Model:** A combination of both content-based and collaborative 
filtering techniques.

### 4. Model Evaluation

After building the model, we test its performance and ensure recommendations 
represent what users actually want.

**Initial Evaluation:**
- Tune the model parameters
- Test on the reserved test dataset
- Validate recommendation quality

**User Testing:**
- Experiment with recommendations on a user group
- Collect user feedback and ratings
- Track metrics such as:
  - Click-through rates on recommendations
  - Purchase rates for recommended products
  - User satisfaction scores
  - Other relevant business metrics

### 5. Model Deployment and Monitoring

Once building and testing are complete, the model goes to production as part 
of the beauty product app and website.

**Ongoing Responsibilities:**
- Track deployed model performance continuously
- Ensure the model continues meeting business requirements
- Plan future iterations based on new information
- Retrain the model to expand capabilities as needed

## Key Takeaways

**Important Principles:**
- Each step of the machine learning model lifecycle is critical to solution 
  success
- After deployment, continuous monitoring and improvement are required to 
  maintain solution quality
- The process is iterative, with opportunities for refinement at each stage
- Real-world feedback is essential for validating model effectiveness

**Time-Intensive Processes:**
- Data collection and preparation typically consume the most time
- Model evaluation requires careful attention to ensure quality
- Ongoing monitoring and maintenance are continuous responsibilities

The machine learning engineer's role involves managing this entire lifecycle, 
from initial problem definition through ongoing model maintenance, ensuring 
that technical solutions deliver genuine business value.

---

*This content is adapted from the "A Day in the Life of a Machine Learning 
Engineer" video lesson from the IBM AI Engineering Professional Certificate 
course.*
