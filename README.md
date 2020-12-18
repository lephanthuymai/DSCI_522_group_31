
Online Purchasing Intention Predictor
=====================================

Co-authors: Mai Le, Yazan Saleh, Tran Doan Khanh Vu, Jingjing Zhi

A data analysis project aiming to predict purchasing intentions of
online shoppers.

About
-----

In this project, we compare 3 different algorithms with the aim of
building a classification model to predict purchasing intentions of
online shoppers given browser session data and pageview data. We also
tried each algorithm with both setting the weights so that the classes
are “equal” (`class_weight="balanced"`) and SMOTE to see which approach
will better address the class imbalance issue. Given our dataset, random
forest classifier with SMOTE was identified as the best model compared
to support vector machine and logistic regression classifiers. Although
the model performed relatively well in terms of accuracy with a score of
0.89, its performance was less robust when scored using `f1` metric.
Specifically, the model had an `f1` score of 0.67 and mis-classified 336
observations, 146 of which were false negatives. The 146 incorrect
classifications are significant as they represent potential sources of
missed revenue for e-commerce businesses. Therefore, we recommend
improving this model prior to deployment in the real-world.

The data set used in this project is the “Online Shoppers Purchasing
Intention” dataset provided by the [Gözalan
Group](http://www.gozalangroup.com.tr/) and used by Sakar et. al in
their analysis published in [Neural Computing and
Applications](https://link.springer.com/article/10.1007/s00521-018-3523-0)
(Sakar et al. 2019). The data set was sourced from UCI’s Machine
Learning Repository (Dua and Graff 2017) at this
[link](https://archive.ics.uci.edu/ml/datasets/Online+Shoppers+Purchasing+Intention+Dataset).
The specific file used for the analysis found
[here](https://archive.ics.uci.edu/ml/machine-learning-databases/00468/online_shoppers_intention.csv).
Each row in the data set contains pageview and session information
belonging to a different visitor that browsed
[Columbia](https://www.columbia.com.tr), an online e-commerce platform
based in Turkey. Each row also contains the target class `REVENUE`, a
boolean flag indicating whether that user session contributed to revenue
or not. Pageview data includes the type of pages that the visitor
browsed to and the duration spent on each page. Session information
includes visitor-identifying data such as browser information, operating
system information as well visitor location and type.

Reports
-------

The final report can be found
[here](https://htmlpreview.github.io/?https://github.com/UBC-MDS/DSCI_522_group_31/blob/main/reports/report.html)

Usage
-----

To replicate this analysis, please follow these steps:

### Step 1: Clone this GitHub repository

### Step 2A: Using Docker

*note - the instructions in this section also depends on running this in
a unix shell (e.g., terminal or Git Bash)*

To replicate the analysis, install
[Docker](https://www.docker.com/get-started). Then run the following
command at the command line/terminal from the root directory of this
project:

    docker run --rm -v /$(pwd):/home/online_shopping_predictor lephanthuymai/dsci_522_group_31:latest make -C /home/online_shopping_predictor all

To reset the repo to a clean state, with no intermediate or results
files, run the following command at the command line/terminal from the
root directory of this project:

    docker run --rm -v /$(pwd):/home/online_shopping_predictor lephanthuymai/dsci_522_group_31:latest make -C /home/online_shopping_predictor clean

### Step 2B: Without using Docker

Create and activate a conda environment using the `env.yaml` at the root
of this project by running the following command at the root directory
of the project. (Alternatively, you can manually install the
dependencies listed in the `env.yaml` file)

    conda env create --file env.yaml
    conda activate online_shopping_prediction_env

Run the following commands at the command line/terminal from the root
directory of this project:

    make all

![Makefile Dependency Graph](img/Makefile.png)

To reset the project to a clean state and re-run the analysis, run the
following command at the command line/terminal from the root directory
of the project:

    make clean

Dependencies
------------

Please see the project dependencies included in the root env.yaml file.

If you choose to not use `Docker` to run the project, you also need to have [Chromium 88](https://www.google.com/intl/en_ca/chrome/beta/) installed. This is a requirement for plot generation and saving through `altair`.

License
-------

All Online Purchasing Intention Predictor materials are made available
under the **Creative Commons Attribution 2.5 Canada License** ([CC BY
2.5 CA](https://creativecommons.org/licenses/by/2.5/ca/)).

References
==========

<div id="refs" class="references hanging-indent">

<div id="ref-Dua:2019">

Dua, Dheeru, and Casey Graff. 2017. “UCI Machine Learning Repository.”
University of California, Irvine, School of Information; Computer
Sciences. <http://archive.ics.uci.edu/ml>.

</div>

<div id="ref-Sakar2019">

Sakar, C. Okan, S. Olcay Polat, Mete Katircioglu, and Yomi Kastro. 2019.
“Real-Time Prediction of Online Shoppers’ Purchasing Intention Using
Multilayer Perceptron and Lstm Recurrent Neural Networks.” *Neural
Computing and Applications* 31 (10): 6893–6908.
<https://doi.org/10.1007/s00521-018-3523-0>.

</div>

</div>
