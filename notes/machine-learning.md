# Machine learning for regular programmers.

<!-- vim-markdown-toc GFM -->

* [Why?](#why?)
    * [Success criteria For this post](#success-criteria-for-this-post)
* [ML at 10,000 feet](#ml-at-10,000-feet)
    * [What problems can ML solve](#what-problems-can-ml-solve)
        * [Classification](#classification)
        * [Regression](#regression)
        * [Clustering](#clustering)
        * [Dimension Reduction](#dimension-reduction)
    * [The ML steps](#the-ml-steps)
        * [Requirements gathering (problem definition)](#requirements-gathering-(problem-definition))
        * [Data analysis](#data-analysis)
        * [Data preparation (pre-processing in SciKit)](#data-preparation-(pre-processing-in-scikit))
        * [Model Selection](#model-selection)
        * [Training](#training)
        * [Evaluation](#evaluation)
        * [Hyper parameter tuning](#hyper-parameter-tuning)
        * [Validation](#validation)
        * [Present Results, Use it](#present-results,-use-it)
    * [Categories of ML](#categories-of-ml)
        * [Supervised vs Unsupervised vs Semi Supervised](#supervised-vs-unsupervised-vs-semi-supervised)
        * [Batch vs Online](#batch-vs-online)
    * [The ML learning challenges](#the-ml-learning-challenges)
    * [How to measure the effectiveness of ML](#how-to-measure-the-effectiveness-of-ml)
        * [Precision and Recall](#precision-and-recall)
        * [Accuracy](#accuracy)
        * [Failures:  Google Photos recognizing black people as gorillas](#failures:--google-photos-recognizing-black-people-as-gorillas)
        * [Failures:  HP face tracking doesn't recognize black people](#failures:--hp-face-tracking-doesn't-recognize-black-people)
* [Computing Power, Hardware,](#computing-power,-hardware,)
    * [Why can't big computer do all of it](#why-can't-big-computer-do-all-of-it)
    * [Why GPU vs CPU](#why-gpu-vs-cpu)
    * [What is tensor flow](#what-is-tensor-flow)
    * [Tensor flow is hard, are there alternatives](#tensor-flow-is-hard,-are-there-alternatives)
        * [What does on device ML cores do](#what-does-on-device-ml-cores-do)
    * [Model building vs Model Execution](#model-building-vs-model-execution)
    * [Computation power required for cat pictures](#computation-power-required-for-cat-pictures)
* [Misc](#misc)
    * [Why is ML stuff so complicated](#why-is-ml-stuff-so-complicated)
    * [ML Optical Illusions](#ml-optical-illusions)
* [Resources](#resources)
    * [What should I read to learn more](#what-should-i-read-to-learn-more)

<!-- vim-markdown-toc -->

## Why?

When I started programming ML was very weak, and I basically ignored it. Like all technology, ML has gotten cheaper and more powerful. And like many hot technologies, it's become full of hype. Here's my attempt to build a high level understanding of ML

### Success criteria For this post

* I have a good enough understanding of ML to tell if someone is full of shit.
* I can explain ML to a PM or executive.
* I know the problems ML can solve.
* I know the common words used in ML.
* I can make some PoC projects to test my understanding.
* I can tell if a problem can be solved by ML.
* I can keep track of the ML concepts I've learned and cross check them with a PhD.

## ML at 10,000 feet

ML is the ability for computers to build algorithms without explicit programming by having the algorithm be inferred by data. This is especially powerful as the computer can usually find patterns in large data sets that are too complicated for humans to find and express.

### What problems can ML solve

#### Classification

Given a sample, classify into a discrete set of known values.  Mathematically F(sample):Enum. Training data must be labelled, into a discrete set of data.

Classification can be binary (spam detection), or categorical (image recognition, sentiment analysis, speech recognition). Many classifier provide a confidence score (I'm 90% sure this is a cat, but 20% sure it's dog).

Algorithms used include decision trees, and Baseyian classifiers.

#### Regression

Given a sample, what is the output value.  Mathematically F(sample):Number.  Determine F.

For example, how much does age impact the probability of having cancer. Given an income, what is the happiness quotient. Linear Regression has been around for a long time (you might remember newton's method from high school)


#### Clustering

Given a set of unlabeled data, classify it into groups.  Mathematically F(List[Data]):List[Set(Data)].

For example, given all netflix users, these are the group of users which are similar. The categories can then be combined with regression to determine which groups of movies a set of users would enjoy.

Another example is given a social network, deduce the communities.

Another example is anomaly detection. Amazingly I have a published [paper](https://www.microsoft.com/en-us/research/publication/perfaugur-robust-diagnostics-for-performance-anomalies-in-cloud-services/) on anomaly detection.

Algorithms used include decision trees, and Baseyian classifiers.

#### Dimension Reduction


### The ML steps

Just like traditional programming progresses through requirements, design, implementation, and testing there is set of steps required for ML.

#### Requirements gathering (problem definition)
#### Data analysis
#### Data preparation (pre-processing in SciKit)
#### Model Selection
#### Training
#### Evaluation
#### Hyper parameter tuning
#### Validation
#### Present Results, Use it

### Categories of ML

#### Supervised vs Unsupervised vs Semi Supervised
#### Batch vs Online
In batch learning the model is built once, and ignores incoming data.

In online learning (better called incremental learning) an initial model is deployed but is then re-deployed with an updated model based on the incoming data. The rate at which the model is updated is the Learning Rate, and is an important parameter, if the model is updated quickly, it can break quickly based on a string of un-representative data, if the model is updated slowly there can be a prologed period of time while the model performance ispoor.

* Instance vs Model

### The ML learning challenges

* Insufficient Training Data
* Non-representative training data
* Low quality data
* Incorrect features
* Over fitting the data
* Under fitting the data (choosing the wrong model)


### How to measure the effectiveness of ML

#### Precision and Recall
#### Accuracy
#### Failures:  Google Photos recognizing black people as gorillas
From: https://www.theverge.com/2015/7/1/8880363/google-apologizes-photos-app-tags-two-black-people-gorillas

Google came under fire this week after its new Photos app categorized photos in one of the most racist ways possible. On June 28th, computer programmer Jacky Alciné found that the feature kept tagging pictures of him and his girlfriend as "gorillas." He tweeted at Google asking what kind of sample images the company had used that would allow such a terrible mistake to happen.

Google attempted to fix the algorithm, but ultimately removed the gorilla label altogether. Zunger noted that the company is working on longer-term fixes that revolve around which labels could be problematic and better recognition of dark-skinned faces.

#### Failures:  HP face tracking doesn't recognize black people


## Computing Power, Hardware,

### Why can't big computer do all of it

### Why GPU vs CPU

CPU's are optimized for integer operations on few threads (E.g. high end CPU has 8 threads). GPUs are optimized for parallel floating point optimization (E.g.high end GPU has 560K threads).

### What is tensor flow

Tensor flow is a library that lets you build models (as opposed to just use models like scikit-learn), and have the models be compiled to GPU/CPU on device ML processors.

### Tensor flow is hard, are there alternatives

#### What does on device ML cores do

### Model building vs Model Execution

### Computation power required for cat pictures


## Misc

### Why is ML stuff so complicated


### ML Optical Illusions


## Resources

### What should I read to learn more

[Hands on machine learning with SciKit-Learn and tensor flow](https://www.amazon.com//dp/1491962291)

