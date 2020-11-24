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

### Create model flow

To create an initial machine learning flow:

1. From the Assets page, click Add to project.
2. In the Choose asset type page, select Modeler Flow.
3. On the Modeler page, select the ‘From File’ tab.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/create-flow.png?raw=true)


4. Download the model flow that is named ‘customer-churn-flow.str’ from the data folder which you downloaded earlier or you can download the repository [here](https://github.com/fawazsiddiqi/WatsonSPSS).

5. Drag the downloaded modeler flow file to the upload area. This also sets the name for the flow.

6. Change the name and provide a description for the machine learning flow (optional).

7. Click Create. This opens the Flow Editor that can be used to create a machine learning flow.

You have now imported an initial flow that we’ll explore in the rest of this tutorial.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/initial-flow.png?raw=true)

Under the **Modeling** drop-down menu, you can see the various supported modeling techniques. The first one is Auto Classifier, which tries several techniques and then presents the results of the best one.

The main flow itself defines a pipeline consisting of several steps:

- A Data Asset node for importing the data set
- A Type node for defining metadata for the features, including a selection of the target attributes for the classification
- An Auto Data Prep node for preparing the data for modeling
- A Partition node for partitioning the data into a training set and a testing set
- An Auto Classifier node called ‘churn’ for creating and evaluating the model

Additional nodes have been associated with the main pipeline for viewing the input and output. These are:

- A Table output node called ‘Input Table’ for previewing the input data
- A Data Audit node called ’21 fields’ (default name) for auditing the quality of the input data set (min, max, standard, and deviation)
- An Evaluation node for evaluating the generated model
- A Table output node called ‘Result Table’ for previewing the results of the test prediction

Other input and output types can be viewed by selecting the **Outputs** drop-down menu.

### Assign data asset and run the flow

To run the flow, you must first connect the flow with the appropriate set of test data available in your project.

1. Select the three dots of the Data Asset node to the left of the flow (the input node).

2. Select the **Open** command from the menu. This shows the attributes of the node in the right part of the page.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/data-asset-properties.png?raw=true)

3. Click **Change data asset** to change the input file.

4. On the next page, select your .CSV file that contains the customer churn, and click OK.

5. Click **Save**.

6. Click **Run** (the arrow head) in the toolbar to run the flow.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/run-command.png?raw=true)

Running the flow creates a number of outputs or results that can be inspected in more detail.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/run-and-output.png?raw=true)