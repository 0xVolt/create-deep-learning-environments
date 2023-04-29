# Setup Jupyter Lab for Deep Learning
Before you continue on, it's important to note that this tutorial was intended for setting up virtual environments on a Linux system. While this process is similar on other OSs, some commands might differ so it's worth referring to the documentation at each step.  

## Table of Contents
- [Setup Jupyter Lab for Deep Learning](#setup-jupyter-lab-for-deep-learning)
  - [Table of Contents](#table-of-contents)
  - [Steps](#steps)
    - [Setting up the Virtual Environment](#setting-up-the-virtual-environment)
    - [Linking the Virtual Environment to a Jupyter Kernel](#linking-the-virtual-environment-to-a-jupyter-kernel)
    - [Installing the Required Libraries](#installing-the-required-libraries)
    - [Installing our GPU Drivers](#installing-our-gpu-drivers)


## Steps
These are the steps to initialise a virtual environment for any deep learning project in Jupyter Lab. They're as follows:

### Setting up the Virtual Environment
1. **Set the `conda` environment to `base` so you can launch Jupyter Lab**

2. **`cd` into the directory** you're working in

3. **Create a Python `venv`** with the command:
   ```shell
   python3 -m venv <name_of_venv>
   ```

4. **Activate the `venv`** with the command:
   ```shell
   source <name_of_venv>/bin/activate
   ```

   You can deactivate the `venv` when you're done with the project with:
   ```shell
   deactivate
   ```

### Linking the Virtual Environment to a Jupyter Kernel
5. **Install `ipykernel`** to link our `venv` with a Jupyter kernel (which is another word for environment or runtime). This is a one-time installation. If you've got `ipykernel` installed, you don't have to again. We do this with:
   ```shell
   pip install ipykernel
   ```
   *Note: You can list out all the libraries installed with the command:*
   ```shell
   pip list
   ```

6. **Link the kernel to Jupyter Lab's** runtime using:
   ```shell
   python3 -m ipykernel install --user --name=<name_of_venv>
   ```

   The command-line should output,
   ```shell
   Installed kernelspec ImageClassification in /home/usr/.local/share/jupyter/kernels/<name_of_venv>
   ```

   *Note: You can list out all the jupyter kernels you've got with:*
   ```shell
   jupyter kernelspec list
   ```

   This is now what should come up if this is the first kernel you create:
   ```shell
   Available kernels:
      python3                /home/usr/anaconda3/share/jupyter/kernels/python3
      <name_of_venv>         /home/usr/.local/share/jupyter/kernels/<name_of_venv>
   ```

   *Also, you can uninstall a kernel with:*
   ```shell
   jupyter kernelspec uninstall <name_of_venv>
   ```

### Installing the Required Libraries
The `tensorflow` and Google `protobuf` libraries have compatibility issues so come back to this if it doesn't work.

7. Install `tensorflow` into your kernel by running this in a notebook cell:
   ```py
   !pip install tensorflow
   ```

   Be wary of an error with Google's Python dependencies within tensorflow. They can be solved using this block of code to update pip's installs of Google's libraries.
   ```shell
   pip uninstall protobuf
   pip uninstall google
   pip install google 
   pip install --upgrade protobuf
   ```

   *Note: You may also need to upgrade pip itself. You do so with:*
   ```shell
   pip install --upgrade pip
   ```

### Installing our GPU Drivers 
**Different versions of PyTorch require specific versions of CUDA and cuDNN libraries. You can check the compatible versions in the official PyTorch documentation. For example, for PyTorch 1.10.0, the compatible CUDA version is 11.3 and the compatible cuDNN version is 8.2.1.**

> It's important to install the correct versions to avoid compatibility issues and ensure optimal performance.

8. 