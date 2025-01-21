# Model-Based Deep Learning
In this repository we include the source code accompanying our recent book:

Nir Shlezinger and Yonina C. Eldar, "Model-Based Deep Learning", 2023.

## Book Abstract
Signal processing traditionally relies on classical statistical modeling techniques. Such model-based methods utilize mathematical formulations that represent the underlying physics, prior information and additional domain knowledge. Simple classical models are useful but sensitive to inaccuracies and may lead to poor performance when real systems display complex or dynamic behavior. 
More recently, deep learning approaches that use highly  parametric deep neural networks are becoming increasingly popular. Deep learning systems do not rely on mathematical modeling, and learn their mapping from data, which allows them to operate in complex environments. However, they lack the interpretability and reliability of model-based methods, typically require large training sets to obtain good performance,  and tend to be computationally complex.
 
Model-based signal processing methods and data-centric deep learning each have their pros and cons. These  paradigms can be characterized  as edges of a continuous spectrum varying in specificity and parameterization. The methodologies that lie in the middle ground of this spectrum, thus integrating model-based signal processing with deep learning, are referred to as model-based deep learning, and are the focus  here. 
  
This monograph provides a tutorial style presentation of model-based deep learning methodologies. These are families of algorithms  that combine principled mathematical models with data-driven systems to benefit from the advantages of both approaches. Such model-based deep learning methods exploit both partial domain knowledge, via mathematical structures designed for specific problems, as well as learning from limited data.  We accompany our presentation with  running signal processing examples, in super-resolution, tracking of dynamic systems, and array processing. We show how they are expressed using the provided characterization and specialized in each of the detailed methodologies.  Our aim is to facilitate the design and study of future systems at the intersection of signal processing and machine learning that incorporate the advantages of both domains. The source code of our numerical examples are available and reproducible as Python notebooks.

## Simulation Code
The simulation code is given in Python Notebook format. All notebooks are completely self-contained and can be launched without any external dependcies using online platforms such as Google Colab. As a result, no hardware or software requirements are needed, and only a Google Colab account is sufficient for being able to run and display the code in a step-by-step manner. The notebooks are particularly suitable to accompany a course on model-based deep learning, and were designed to support in-class display.

The notebooks are enumerated based on their example index in the book. They are thus divided based on the chapters including numerical examples, which are Chapter 3 (model-based methods) and Chapter 5 (model-based deep learning) of the book.

## Acknowledgements
We are grateful to our students who helped us in fleshing up this repository. We particularly thank Elad Sofer, who lead the experimental effort and its packing as accessible notebooks.


# SubspaceNet: Deep Learning-Aided Subspace Methods for DoA
This repository includes the source code used in our recent paper:

Dor H. Shmuel, Julian P. Merkofer, Guy Revach, Ruud J. G. van Sloun, and Nir Shlezinger,
["SubspaceNet: Deep Learning-Aided Subspace Methods for DoA Estimation"](https://arxiv.org/abs/2306.02271)

## Absract
Direction of arrival (DoA) estimation is a fundamental task in array processing. A popular family of DoA estimation algorithms are subspace methods, which operate by dividing the measurements into distinct signal and noise subspaces. Subspace methods, such as MUSIC and Root-MUSIC, rely on several restrictive assumptions, including narrow-band non-coherent sources and fully calibrated arrays, and their performance is considerably degraded when these do not hold.
In this work we propose SubspaceNet; a data-driven DoA universal estimator which learns how to divide the observations into distinguishable subspaces. This is achieved by utilizing a dedicated deep neural network to learn the empirical autocorrelation of the input, by training it as part of the Root-MUSIC method, leveraging the inherent differentiability of this specific DoA estimator, while removing the need to provide a ground-truth decomposable autocorrelation matrix. Once trained, the resulting SubspaceNet serves as a universal surrogate covariance estimator that can be applied in combination with any subspace-based \ac{doa} estimation method, allowing its successful application in challenging setups. SubspaceNet is shown to enable various DoA estimation algorithms to cope with coherent sources, wideband signals, low SNR, array mismatches, and limited snapshots, while preserving the interpretability and the suitability of classic subspace methods. 

## Overview
This repository consists of following Python scripts:
* `main.py` this scripts is the interface for applying the proposed algorithms, by wrapping all the required procedures and parameters for the simulation.
* `src.training.py` handling the simulation of the algorithms, including the training and evaluation stage.
* `src.criterions.py` defines document several loss functions (RMSPELoss and MSPELoss).
* `src.data_handler.py` handles the creation and processing of synthetic datasets based on specified parameters and model types.
* `src.methods.py` defines the classical and model-based methods, which used for simulation.
* `src.models.py` defines the tested NN-models and the model-based DL models, which used for simulation.
* `src.signal_creation.py` defines and creates signals and observations. Inherits from SystemModel class.
* `src.system_model.py` defines the SystemModel class for defining the settings of the DoA estimation system model.
* `src.utils.py` defines some helpful functions.

## Requirements
This script requires that pyenv\requirements.txt will be installed within the Python environment you are running in.

Another option in the activate pyEnv\SubspaceNetEnv python environment.

## Getting started
If you just want to run the code, run main.py script (for nominal scenario, as detiled in the script).
For changing simulation parameters follow the documentaion in main.py script.
