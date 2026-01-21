# Hands-On Machine Learning

This repository contains my work with and content adapted from _Hands-On_
_Machine Learning with Scikit-Learn, Keras, and TensorFlow_ by Aurélien Géron.
More information about the book can be found here:
[https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/](
https://www.oreilly.com/library/view/hands-on-machine-learning/9781492032632/).

> [!TIP]
> Géron maintains repositories which contain supplementary material for the book
> and can be accessed via [github/ageron/handson-ml3](
> https://github.com/ageron/handson-ml3) (or [github/ageron/handson-ml2](
> https://github.com/ageron/handson-ml2) for the second edition).

## Content
The `data` directory contains the datasets necessary to complete the examples
and exercises. The files themselves were sourced from the repositories linked
above.

The `examples` directory contains various example ML applications adapted from
the book and supplementary Jupyter notebooks available in the repositories
linked above.

The `exercises` directory contains my work completing the exercises at the end
of each chapter in the book, including commentary and reasoning for the design
choices made. Within the directory, there is a `exercises_templates` directory
containing Jupyter notebooks that serve as templates for the exercises at the
end of each chapter.

## Machine Learning Project Checklist
This checklist is adapted from the one presented in Chapter 1 and Appendix A.

### Step 1: Frame the Problem and Its Objective
This step is one of the most important steps when undertaking a machine learning
project. In this step, we focus on understanding the problem at hand and should
consider the following questions:

 * What is the objective in solving this problem (in business terms)?
 * How will your solution be applied?
 * Does a solution currently exist? What are its limitations?
 * What kind ML task is your problem? Supervised? Unsupervised? Online? Offline?
 * How will the solution's effectiveness be measured? Does it align with the
   objective?
 * What is the minimum or baseline performance required to meet the objective?
 * Have comparable problems been solved and their solutions available to be
   adapted?

In addition to thoroughly considering these questions, you should also create a
list of any and all assumptions made thus far. Then, if possible, review and aim
to verify your assumptions.

## Step 2: Obtain Necessary Data
This step not only involves locating and obtaining the data necessary to apply
ML to your problem but also aiming to automate this process (if required). More
importantly, you may be required to get authorization or licensing before using
the data in your work. The steps below are common in ML pipelines:

 * Identify what and how much data is required.
 * Locate and document the data source(s).
 * Consider hardware constraints (i.e., how much storage space is needed).
 * Check legal obligations and obtain necessary authorizations.
 * Convert the data into a format compatible with your ML workflow.
 * Ensure that any confidential or sensitive information is removed/protected.
 * Create a test set sample and set it aside (never review--no snooping).

## Step 3: Data Exploration
This step involves an exploration of your data, ideally while gaining insights
from discussions with a field expert. Be sure that in the previous step you
created a test set sample. That sample will be set aside and not analyzed.

 * Create a copy of the data for exploratory analysis.
 * Create a Jupyter notebook to serve as a "lab notebook" of your exploration.
 * Study each attribute and its characteristics.
 * For supervised problems, identify the target attribute(s).
 * Visualize the data to better understand/communicate its characteristics.
 * Document promising transformations and what was learned during exploration.

## Step 4: Data Preprocessing
This step focuses on preprocessing the data for training an ML model. Before we
begin, there are two critical items to note: (1) always work on copies of the
data rather than modifying or manipulating the original copy and (2) functions
should be written for all data transformations for several reasons. These
include the consistency of transformations during future data refreshes, easily
applying transformations in future projects, to clean/prepare the test set, and
to make it easy to treat preprocessing choices as hyperparameters.

 * Data Cleaning
     * If necessary, remove or impute missing values and outliers.
 * Feature Selection (_optional_)
     * Drop attributes that provide no useful information.
 * Feature Engineering (_if appropriate_)
     * Discretize continuous features.
     * Decompose features (i.e., categorical, date/time, etc.).
     * Define promising transformations of features.
     * Create new features from sets of aggregated features.
 * Feature Scaling

## Step 5: Model Exploration and Selection
This step involves exploring different ML models applicable to your task and
creating a short list of the best ones. Note that if the training set is large,
it may be useful to create a small sample of the training set to reduce training
time during exploration. However, reducing the number samples will penalize the
performance of more complex models such as neural networks or random forests.

 * Train models from different categories using standard parameters.
 * Measure and compare performance of models (i.e., via cross-validation).
 * Analyze which variables were deemed "most important" by each method.
 * Analyze the errors that each method made.
 * Perform a quick round of feature selection and engineering.
 * Perform additional iterations on the previous steps.
 * To finish, short-list the top 3 to 5 most promising models. Ideally
   preferring models which make different types of errors.

## Step 6: Model Fine-Tuning and Solution Definition
This step focuses on fine-tuning your models and defining your solution. When
fine-tuning your models, use as much data as possible––especially as you
progress toward the end of fine-tuning. Furthermore, do not adjust any
hyperparameters after measuring the generalization error as doing so will likely
result in overfitting.

 * Fine-tune hyperparameters using cross-validation. This includes treating the
   data preprocessing choices as hyperparameters (especially if there is doubt).
 * Experiment with ensemble methods.
 * Once confident with your final model, measure its performance on the test set
   to estimate the generalization error.

## Step 7: Solution Presentation
This step involves sufficiently documenting the work leading up to and including
your solution, as well as preparing visuals to effectively convey the solution.

 * Document the process.
 * Create a presentation that starts with highlighting the big picture.
 * Justify how your solution achieves the objective.
 * Be sure to note interesting findings throughout the process.
 * Ensure key findings are conveyed via visualizations or easy-to-remember
   statements.

## Step 8: Solution Launch and Maintenance
This step involves building the infrastructure necessary to deploy, monitor, and
maintain your solution.

 * Prepare the solution for production.
 * Write monitoring code to check your solution's live performance at regular
   intervals––triggering alerts when performance degrades.
 * Retrain model(s) on a regular basis using fresh data (automate this!).
