.. _customerchurn:

CustomerChurn 
===============

1. CustomerChurn workflow

   * Dataset
2. Create a Notebook
3. Download the data and notebook

   * Upload CustomerChurn pipeline notebook file
4. Explore the ML code of the CustomerChurn usecase
5. Convert your notebook to a Katonic Pipeline
6. Katonic Pipeline Dashboard
7. Pipeline components execution

CustomerChurn workflow
-------------------------------
* Load the e_commerce dataset.
* Transforms raw data into meaningful information by doing data preprocessing.
* Splitting the data into training and testing sets.
* X and Y axis labels for graphs or figures.
* Training the different models
* Evaluating the different modes and choosing the best model among them.

**What we're going to build**

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/overview_graph.png
   :scale: 50%
   :align: center

Dataset
+++++++

The dataset involved here is publicly available at `CustomerChurn Dataset <https://www.kaggle.com/blastchar/telco-customer-churn>`_ that predict the behaviour to retain customers and developed focused customer retention program, given all the information in the dataset. 

Create a Notebook
------------------

Navigate to the **Notebook** link on the Katonic central dashboard.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/notebook.png
   :scale: 40%
   :align: center

Click on **Create Notebook**

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/create.png
   :scale: 40%
   :align: center

Specify a name for your Notebook

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/notebook_name.png
   :scale: 40%
   :align: center

Make sure you have selected one of the image:

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/choose_image.png
   :scale: 80%
   :align: center

Select the **CPU** and **Memory** require:

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/cpu_mo.png
   :scale: 80%
   :align: center

Click **Create** to create the notebook.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/create2.png
   :scale: 80%
   :align: center

When the notebook server is available, click Connect to connect to it.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/connect.png
   :scale: 70%
   :align: center

Download the data and notebook
-----------------------------------

A new tab will open up with the JupyterLab landing page. Create a new Terminal in JupyterLab.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/terminal.png
   :scale: 40%
   :align: center

Upload CustomerChurn pipeline notebook file
++++++++++++++++++++++++++++++++++++++++++++
In the Terminal window, run these commands and download the notebook and the data that you will use for the remainder of the lab.

.. note:: 
   
   git clone https://github.com/katonic-dev/Examples.git
   
This repository contains a series of curated examples with data and annotated Notebooks. Navigate to the folder in the sidebar and open the notebook `customer_churn.ipynb <https://github.com/katonic-dev/Examples/blob/master/customer_churn/customer_churn.ipynb>`_ inside **Examples/customerchurn/**.

Explore the ML code of the CustomerChurn usecase
-----------------------------------------------------

Run the notebook step-by-step. Note that the code fails because a library is missing.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/missing_lib.png
   :scale: 40%
   :align: center

You can install the required libraries either by go to the Terminal and install the missing library or directly in the cell in the notebook.

Run the cell right above to install the missing libraries:

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/pip_install.png
   :scale: 40%
   :align: center

Restart the notebook kernel by clicking on the Refresh icon.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/restart.png
   :scale: 40%
   :align: center

Convert your notebook to a Katonic Pipeline
----------------------------------------------

Enable Kale by clicking on the Kale slider in the Kale Deployment Panel (left pane of the notebook).

**Kale:**

* Kale is a project that aims at simplifying the Data Science experience of deploying Pipelines workflows.

* Kale bridges this gap by providing a simple UI to define Kubeflow Pipelines workflows directly from you JupyterLab interface, without the need to change a single line of code.

* Kale was designed to address difficulties by providing a tool to simplify the deployment process of a Jupyter Notebook into Katonic Pipelines workflows. Translating Jupyter Notebook directly into a Katonic pipeline ensures that all the processing building blocks are well organized and independent from each other, while also leveraging on the experiment tracking and workflows organization.

* Kale takes as input the annotated Jupyter Notebook and generates a standalone Python script that defines the Katonic pipeline, based on the Notebook and Cells annotations.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/kale.png
   :scale: 40%
   :align: center

Explore per-cell dependencies. 

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/kale_deploy.png
   :scale: 40%
   :align: center

See how multiple notebook cells can be part of a single pipeline step, as indicated by color bars on the left of the cells, and how a pipeline step may depend on previous ones, as indicated by depends on labels above the cells. For example, the image below shows multiple cells that are part of the same pipeline step. They have the same brown color and they depend on a previous pipeline step named "load_data".

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/tag.png
   :scale: 40%
   :align: center

Normally, you should create a new Docker image to be able run this notebook as a Katonic pipeline, to include the newly installed libraries.

Click **Advanced Settings** and add Docker image 

**Docker image:** 

* Docker is a tool for running applications in an isolated environment. It gives you advantages similar to running your applications inside a virtual machine. 

* Docker gives you these advantages but without the overhead and hassle of running and managing a virtual machine instead we have containers, the code and the environment are all wrapped up inside a container but a container is not a full virtual machine. 

* Docker uses special features of the UNIX file system to create these isolated environments.

* Images are defined using a docker file, a docker file is just a text file with a list of steps to perform to create that image. So, you write a docker file then you build that and you get an image which you can run to get containers.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/adv_set.png
   :scale: 50%
   :align: center

Click the **Volume access mode** and select the mode.

* ReadOnlyMany - Read only by many node

* ReadWriteOnce - Read write by single node

* ReadWriteMany - Read write by many node

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/mode.png
   :scale: 50%
   :align: center

Click the **Compile and Run** button.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/comp_run.png
   :scale: 50%
   :align: center

Watch the progress of Compiling Notebook.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/comp.png
   :scale: 50%
   :align: center

Watch the progress of Running pipeline

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/run.png
   :scale: 50%
   :align: center

Click the link to go to the Katonic Pipelines UI and view the run.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/common_images/view.png
   :scale: 50%
   :align: center

Katonic Pipeline Dashboard
----------------------------

After clicking view, select the customerchurn experiment

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/act_exp.png
   :scale: 40%
   :align: center

Dropdown the experiment and select the latest pipeline which is created

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/rec_pipe.png
   :scale: 40%
   :align: center

Wait for it to complete.

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/pipe_start.png
   :scale: 40%
   :align: center

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/pipe_comp.png
   :scale: 80%
   :align: center

Pipeline components execution
-------------------------------

Visualization of CustomerChurn Load data Components

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/load_vis.png
   :scale: 40%
   :align: center

Visualization of CustomerChurn Data preprocessing Components

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/prepro_vis.png
   :scale: 40%
   :align: center

Visualization of CustomerChurn Decision tree model Components

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/dt_model_vis.png
   :scale: 40%
   :align: center

Visualization of CustomerChurn Model evaluation Components

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/dt_model_vis.png
   :scale: 40%
   :align: center


Visualization of CustomerChurn Model evaluation Components

.. figure:: https://raw.githubusercontent.com/katonic-dev/KatonicDocumentation/master/docs/source/images/customerchurn/model_eval_vis.png
   :scale: 40%
   :align: center

Congratulations! You just ran an end-to-end Katonic Pipeline starting from your notebook!
