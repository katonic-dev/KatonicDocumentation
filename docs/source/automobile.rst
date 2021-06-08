.. _automobile:

Automobile 
============

1. Automobile workflow

   * Dataset
2. Create a Notebook
3. Download the data and notebook

   * Upload Automobile pipeline notebook file
4. Explore the ML code of the Automobile usecase
5. Convert your notebook to a Katonic Pipeline
6. Katonic Pipeline Dashboard
7. Pipeline components execution

Automobile workflow
-------------------
* Load the automobile dataset.
* Transforms raw data into meaningful information by doing data preprocessing.
* Perform feature engineering to create features.
* Storing created features in the feature store.

**What we're going to build**

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/overview_graph.png
   :scale: 80%
   :align: center

Dataset
+++++++

The dataset involved here is publicly available at `Automobile Dataset <https://www.kaggle.com/toramky/automobile-dataset>`_ that predict the price of the automobiles given all the information in the dataset. 

Create a Notebook
------------------

Navigate to the **Notebook** link on the Katonic central dashboard.

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/notebook.png
   :scale: 40%
   :align: center

Click on **Create Notebook**

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/create.png
   :scale: 40%
   :align: center

Specify a name for your Notebook

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/notebook_name.png
   :scale: 40%
   :align: center

Make sure you have selected one of the image:

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/choose_image.png
   :scale: 80%
   :align: center

Select the **CPU** and **Memory** require:

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/cpu_mo.png
   :scale: 80%
   :align: center

Click Create to create the notebook.

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/create2.png
   :scale: 80%
   :align: center

When the notebook server is available, click Connect to connect to it.

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/connect.png
   :scale: 70%
   :align: center

Download the data and notebook
-----------------------------------

A new tab will open up with the JupyterLab landing page. Create a new Terminal in JupyterLab.

.. figure:: https://github.com/katonic-dev/KatonicDocumentation/blob/master/docs/source/images/terminal.png
   :scale: 40%
   :align: center

Upload Automobile pipeline notebook file
++++++++++++++++++++++++++++++++++++++++++++
In the Terminal window, run these commands and download the notebook and the data that you will use for the remainder of the lab.

.. note:: 
   
   git clone https://github.com/katonic-dev/Examples.git
   
This repository contains a series of curated examples with data and annotated Notebooks. Navigate to the folder in the sidebar and open the notebook `automobile-preprocessing.ipynb <https://github.com/katonic-dev/Examples/blob/master/automobile/automobile-Deploy.ipynb>`_ inside **Examples/automobile/**.

Explore the ML code of the Automobile usecase
-----------------------------------------------

Convert your notebook to a Katonic Pipeline
----------------------------------------------

Katonic Pipeline Dashboard
----------------------------

Pipeline components execution
-------------------------------
