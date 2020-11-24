# Build your Machine Learning models the easy way with SPSS

## Introduction

This tutorial explains how to graphically build and evaluate machine learning models by using the SPSS Modeler flow feature in IBM® Watson™ Studio. [IBM Watson SPSS Modeler](https://dataplatform.cloud.ibm.com/docs/content/wsd/spss-modeler.html) flows in Watson Studio provide an interactive environment for quickly building machine learning pipelines that flow data from ingestion to transformation to model building and evaluation, without needing any code. This tutorial introduces the SPSS Modeler components and explains how you can use them to build, test, evaluate, and deploy models.

As with the other tutorials in this learning path, we use a customer churn data set that is available on [Kaggle](https://www.kaggle.com/sandipdatta/customer-churn-analysis/notebook#Churn-Analysis).

#### About the data set


## Prerequisites

To complete this tutorial, you need:
- An [IBM Cloud account](https://ibm.biz/WatsonSPSS)

### Estimated time

It should take you approximately 60 minutes to complete this tutorial.

## Steps

- If you do not have an IBM Cloud account please create one or login into your existing account by clicking [here](https://ibm.biz/WatsonSPSS)

- Please make sure that you have cloned/downloaded this repository

### Setup your environment 

1. Create an IBM Cloud Object Storage service.
2. Create an IBM Watson Studio project.
3. Provision IBM Cloud services.
4. Upload the data set.

You must complete these steps before continuing with the learning path. If you have finished setting up your environment, continue with the next step, creating a model flow.

**1. Create a Watson Studio Service**

Once logged in, search for Watson Studio and create a lite instance.

![WatsonSearch](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/ws1.png?raw=true)


![WatsonSearch](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/ws2.png?raw=true)

**2. Create IBM Cloud Object Storage service**

To create an IBM Cloud Object Storage service, search for Object Storage and create a lite instance.

![OB1](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/ob1.png?raw=true)

![OB2](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/ob2.png?raw=true)

**3. Create a Watson Machine Learning Service instance**

To create a Watson Machine Learning instance, search for Machine Learning and create a lite instance.

![wml](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/wml1.png?raw=true)

![wml](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/wml2.png?raw=true)

**4. Upload data set**

- Clone this repository or download this repository 

```script
git clone https://github.com/fawazsiddiqi/WatsonSPSS
``` 
![git](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/git1.png?raw=true)

In Watson Studio, go to the assets tab, and drag and drop the ```customer-churn-kaggle.csv``` from the Data folder from the repository which you just downloaded/cloned

![asset](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/asset.png?raw=true)

