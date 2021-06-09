.. _iris:

Iris
============

1. Iris workflow

   * Dataset
2. Create a Notebook
3. Download the data and notebook

   * Upload Iris pipeline notebook file
4. Explore the ML code of the Iris usecase
5. Convert your notebook to a Katonic Pipeline
6. Katonic Pipeline Dashboard
7. Pipeline components execution

Iris workflow
-------------------
* Load the Iris dataset.
* Transforms raw data into meaningful information by doing data preprocessing.
* Storing created features in the feature store.

**What we're going to build**

.. figure:: /images/iris/overview_graph.png
   :scale: 80%
   :align: center

Dataset
+++++++

The dataset involved here is publicly available at `Iris Dataset <https://www.kaggle.com/uciml/iris>`_  that predict the species of the iris flower, given all the information in the dataset.

Create a Notebook
------------------

Navigate to the **Notebook** link on the Katonic central dashboard.

.. figure:: /images/common_images/notebook.png
   :scale: 40%
   :align: center

Click on **Create Notebook**

.. figure:: /images/common_images/create.png
   :scale: 40%
   :align: center

Specify a name for your Notebook

.. figure:: /images/common_images/notebook_name.png
   :scale: 40%
   :align: center

Make sure you have selected one of the image:

.. figure:: /images/common_images/choose_image.png
   :scale: 80%
   :align: center

Select the **CPU** and **Memory** require:

.. figure:: /images/common_images/cpu_mo.png
   :scale: 80%
   :align: center

Click **Create** to create the notebook.

.. figure:: /images/common_images/create2.png
   :scale: 80%
   :align: center

When the notebook server is available, click Connect to connect to it.

.. figure:: /images/common_images/connect.png
   :scale: 70%
   :align: center

Download the data and notebook
-----------------------------------

A new tab will open up with the JupyterLab landing page. Create a new Terminal in JupyterLab.

.. figure:: /images/common_images/terminal.png
   :scale: 40%
   :align: center

Upload Iris pipeline notebook file
++++++++++++++++++++++++++++++++++++++++++++
In the Terminal window, run these commands and download the notebook and the data that you will use for the remainder of the lab.

.. note:: 
   
   git clone https://github.com/katonic-dev/Examples.git
   
This repository contains a series of curated examples with data and annotated Notebooks. Navigate to the folder in the sidebar and open the notebook `iris-preprocessing.ipynb <https://github.com/katonic-dev/Examples/blob/master/iris/iris-preprocessing.ipynb>`_ inside **Examples/iris/**.

Here we divide the notebook into three steps:

* First step: `iris-preprocessing.ipynb <https://github.com/katonic-dev/Examples/blob/master/iris/iris-preprocessing.ipynb>`_

* Second step: `iris-model-building.ipynb <https://github.com/katonic-dev/Examples/blob/master/iris/iris-model-building.ipynb>`_

* Third step: `iris-deploy.ipynb <https://github.com/katonic-dev/Examples/blob/master/iris/iris-deploy.ipynb>`_

Explore the ML code of the Iris usecase
-----------------------------------------------

Run the notebook step-by-step. Note that the code fails because a library is missing.

.. figure:: /images/iris/missing_lib.png
   :scale: 40%
   :align: center

You can install the required libraries either by go to the Terminal and install the missing library or directly in the cell in the notebook.

Run the cell right above to install the missing libraries:

.. figure:: /images/iris/pip_install.png
   :scale: 40%
   :align: center

Restart the notebook kernel by clicking on the Refresh icon.

.. figure:: /images/iris/restart.png
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

.. figure:: /images/iris/kale.png
   :scale: 40%
   :align: center

Explore per-cell dependencies. 

.. figure:: /images/iris/kale_deploy.png
   :scale: 40%
   :align: center

See how multiple notebook cells can be part of a single pipeline step, as indicated by color bars on the left of the cells, and how a pipeline step may depend on previous ones, as indicated by depends on labels above the cells. For example, the image below shows multiple cells that are part of the same pipeline step. They have the same brown color and they depend on a previous pipeline step named "load_data".

.. figure:: /images/common_images/tag.png
   :scale: 40%
   :align: center

Normally, you should create a new Docker image to be able run this notebook as a Katonic pipeline, to include the newly installed libraries.

Click **Advanced Settings** and add Docker image 

**Docker image:** 

* Docker is a tool for running applications in an isolated environment. It gives you advantages similar to running your applications inside a virtual machine. 

* Docker gives you these advantages but without the overhead and hassle of running and managing a virtual machine instead we have containers, the code and the environment are all wrapped up inside a container but a container is not a full virtual machine. 

* Docker uses special features of the UNIX file system to create these isolated environments.

* Images are defined using a docker file, a docker file is just a text file with a list of steps to perform to create that image. So, you write a docker file then you build that and you get an image which you can run to get containers.

.. figure:: /images/common_images/adv_set.png
   :scale: 50%
   :align: center

Click the **Volume access mode** and select the mode.

* ReadOnlyMany - Read only by many node

* ReadWriteOnce - Read write by single node

* ReadWriteMany - Read write by many node

.. figure:: /images/common_images/mode.png
   :scale: 50%
   :align: center

Click the **Compile and Run** button.

.. figure:: /images/iris/comp_run.png
   :scale: 50%
   :align: center

Watch the progress of Compiling Notebook.

.. figure:: /images/common_images/comp.png
   :scale: 50%
   :align: center

Watch the progress of Running pipeline

.. figure:: /images/common_images/run.png
   :scale: 50%
   :align: center

Click the link to go to the Katonic Pipelines UI and view the run.

.. figure:: /images/common_images/view.png
   :scale: 50%
   :align: center

Katonic Pipeline Dashboard
----------------------------

After clicking view, select the iris experiment

.. figure:: /images/iris/act_exp.png
   :scale: 40%
   :align: center

Dropdown the experiment and select the latest pipeline which is created

.. figure:: /images/iris/rec_pipe.png
   :scale: 40%
   :align: center

Wait for it to complete.

.. figure:: /images/iris/pipe_start.png
   :scale: 40%
   :align: center

.. figure:: /images/iris/pipe_comp.png
   :scale: 40%
   :align: center

Pipeline components execution
-------------------------------

Visualization of Iris Load data Components

.. figure:: /images/iris/load_vis.png
   :scale: 40%
   :align: center

Visualization of Iris Data preprocessing Components

.. figure:: /images/iris/prepro_vis.png
   :scale: 40%
   :align: center


Congratulations! You just ran an end-to-end Katonic Pipeline starting from your notebook!
