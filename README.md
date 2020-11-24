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

### Understanding the data

Now that you have run the flow, take a closer look at the data.

1. Select the **Input Table** node at the top of the flow diagram.

2. Select the three dots in the upper-right corner and invoke the **Profile** command from the pop-up menu.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/preview-input-data-option.png?raw=true)

The last interaction might run part of the flow again but has the advantage that the page provides a Profile tab for profiling the data and a Visualization tab for creating dashboards.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/preview-data-set.png?raw=true)

Now, let’s take a closer look at each of the data columns, such as the values for their minimum, maximum, mean, and standard deviation:

1. Click one level back in the bread crumb list at the top of the page to return to your flow.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/bread-crumb.png?raw=true)

2. Select the **View outputs and versions** command from the upper-right portion of the toolbar.

3. Select the **Outputs** tab.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/outputs-tab.png?raw=true)

4. Double-click the output for the “data audit” node named “21 Fields.” Alternatively, select the three dots associated with the output and select Open from the pop-up menu.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/21-fields-option.png?raw=true)

This gives you an overview like the one in the following image.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/21-fields-output.png?raw=true)

For each feature, the overview shows the distribution in graphical form and whether the feature is categorical or continuous. For numerical features, the computed min, max, mean, standard deviation, and skewness are shown as well. From the column named Valid, you can see that there are 3333 valid values, which means that no values are missing for the listed features and you do not need to bother further with this aspect of preprocessing to filter or transform the columns with lacking values.

### Data preparation

You can change the initial assessment of the features made by the import by using the Type node, which happens to be the next node in the pipeline. To achieve this:

1. Go back to the **Flow Editor** by selecting ```customer-churn-flow``` in the toolbar.

2. Select the **Type** node.

3. Select the **Open** command from the pop-up menu.

This provides a table that shows the features (such as fields), their kind (for example, continuous or flag), and role, along with others.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/type-node-output.png?raw=true)

The Measure can be changed if needed using this node and it is also possible to specify the role of a feature. In this case, the role of the churn feature (which is a Flag with True and False values) has been changed to Target. The Check column might give you more insight into the values of the field.

Click **Cancel** to close the property editor for the **Type** node.

The next node in the pipeline is the **Auto Data Prep** node. This node automatically transforms the data, such as converting categorical fields into numerical ones. To view its results:

1. Select the **Auto Data Prep** node in the flow editor.

2. Select **Open** from the pop-up menu.

This node offers a multitude of settings, for example, for defining the objective of the transformation (optimize for speed or for accuracy).

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/auto-data-prep.png?raw=true)

The previous image shows that the transformation has been configured to exclude fields with too many missing values (threshold is 50) and to exclude fields with too many unique categories. Assume that the latter applies to the phone numbers and don’t worry about them.

The next node in the pipeline is the Partition node, which splits the data set into a training set and a testing set. For the current Partition node, an 80-20 split has been used.


![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/partition-node.png?raw=true)

### Training the model

The next node in the SPSS Modeler flow is the Auto Classifier node named “churn.” This node trains the model based on various build options, such as how to rank and discard generated models (using threshold accuracy).

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/auto-classifier-node.png?raw=true)

If you **Open** the node and select the **BUILD OPTIONS** option from the drop-down menu, you see the property Number of models to use is set to 3, which is the default value. Feel free to change it to a higher number, and then click **Save** to save the changes.

**NOTE:** Remember to rerun the flow if you change any build settings.

### Evaluating the model

To get more details about the generated model:

1. Select the yellow model icon.

2. Select **View Model** from the drop-down menu.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/view-model-option.png?raw=true)

This overview section gives you a list of classifier models and their accuracy. In this example, I set the **Number of models to use** to 10.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/model-evaluation.png?raw=true)

As you navigate through this overview section, you’ll notice that the number of options and views that are associated with each estimator varies. In some cases, a hyperlink is provided to dig down into more details.

For example, take a look at the poor performing ‘C&R’ Tree Model by clicking the name in the table.

On the next page, select the Tree Diagram link to the left to get the tree diagram for the estimator.

You can now hover over either one of the nodes or one of the branches in the tree to get more detailed information about a decision made at a given point.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/tree-diagram.png?raw=true)

Go back by clicking the left arrow in the upper-left part of the page. Then, select the **MPL Neural Network** link to get the details for that estimator. Note that has different options than the tree model.

Click the **Feature Importance** tab.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/feature-importance.png?raw=true)

This graphs the relative performance of each predictor in estimating the model.

Click the **Confusion Matrix** tab.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/model-eval-confusion-matrix.png?raw=true)

The table compares what is predicted versus what it observed. The numbers of correct predictions are shown in the cells along the main diagonal.

If you would like to get the confusion matrix for the complete data set, you can add a Matrix Output node to the canvas.

1. Go back to the flow.

2. Add a **Matrix** node from the Outputs menu.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/matrix-output.png?raw=true)

3. Attach the matrix node to the specified model output node.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/add-matrix.png?raw=true)

**NOTE:** To attach the new node, click the right-side bubble of the existing ‘churn’ model output node and drag the connector to the new matrix node.

4. **Open** the Matrix node.

5. Put the target attribute ‘churn’ in the Rows and the binary prediction ‘$XF-churn’ in the Columns.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/matrix-columns.png?raw=true)

6. For Cell contents, select **Cross-tabulations.**

7. Click **Appearance** and select **Counts, Percentage of Row, Percentage of Column,** and **Include row and column totals**.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/matrix-appearance.png?raw=true)

8. Click **Save**.

9. Run the **Matrix** node.

10. Select **View Output and Versions** in the upper-right corner.

11. Open the output for the Matrix node (named ‘churn x $XF-churn’) by double-clicking it.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/confusion-matrix-pct.png?raw=true)

The main diagonal cell percentages contain the recall values as the row percentages (100 times the proportions metric that’s generally used) and the precision values as the column percentages. The F1 statistics and weighted versions of precision and recall over both categories would need to be manually calculated. The results shown are the combined results applying all three algorithms. If you want to see the results just for the Random Forest, go back to the Auto Classifier node. Open it and uncheck the boxes for all models other than Random Forest. Then, rerun the flow.

If you want to just get the confusion matrix, open the Matrix Output node and unselect ‘Percentage of Row’ and ‘Percentage of Column’ in the appearance section. Then, repeat steps 7-11 above.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/confusion-matrix.png?raw=true)

A more graphical way of showing the confusion matrix can be achieved by using SPSS visualizations. For that purpose, you need to select the Result Table output node, then select the **Profile** option in the drop-down menu.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/results-profile.png?raw=true)

Click the **Visualizations** tab. Then, click **more options** (the double arrow icon) to view the types of charts available. Select the **Treemap** chart.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/treemap-selector.png?raw=true)

Set the **Columns** values to **churn** and $XF-churn, and select **Count** in the **Summary**.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/treemap-visualization.png?raw=true)

Notice that the current pipeline performs a simple split of test and training data using the Partition node. It’s also possible to use cross-validation and stratified cross-validation to achieve slightly better model performance, but at the cost of complicating the pipeline. See the article [k-fold Cross-validation in IBM SPSS Modeler](https://developer.ibm.com/predictiveanalytics/2016/03/02/k-fold-cross-validation-ibm-spss-modeler/) for details on how this can be achieved.

There are two more ways of viewing the results of the evaluation.

1. Go back to the flow editor for the Customer Churn Flow.

2. Select View outputs and version from the top toolbar.

3. Double-click the output named **Evaluation of [$XF-churn] : Gains** to select it.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/model-gains.png?raw=true)

The generated outputs for the model appear.

### Saving and deploying the model

After you create, train, and evaluate a model, you can save and deploy it.

To save the SPSS model:

1. Go back to the flow editor for the model flow.

2. Select the **Predicted Output** node and open its pop-up menu by selecting the 3 dots in the upper-right corner.

3. Select **Save branch as model** from the pop-up menu.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/save-branch-as-model.png?raw=true)

A new window opens.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/save-model.png?raw=true)

4. Type a model name (for example, ‘customer-churn-spss-model’).

5. Click **Save**.

The model is saved to the current project.

The model should now appear in the Models section of the Assets tab for the project.

![spss](https://github.com/fawazsiddiqi/WatsonSPSS/raw/main/images/model-list.png?raw=true)