# Setup Jupyter Lab for Deep Learning
Before you continue on, it's important to note that this tutorial was intended for setting up virtual environments on a Linux system. While this process is similar on other OSs, some commands might differ so it's worth referring to the documentation at each step.  

## Steps
These are the steps to initialise a virtual environment for any deep learning project in Jupyter Lab. They're as follows:
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

5. **Install `ipykernel`** to link our `venv` with a Jupyter kernel (which is another word for environment or runtime). This is a one-time installation. If you've got `ipykernel` installed, you don't have to again. We do this with:
   ```shell
   pip install ipykernel
   ```
   ###### *Note: You can list out all the libraries installed with the command:*
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

   ###### *Note: You can list out all the jupyter kernels you've got with:*
   ```shell
   jupyter kernelspec list
   ```

   This is now what should come up if this is the first kernel you create:
   ```shell
    Available kernels:
        python3                /home/usr/anaconda3/share/jupyter/kernels/python3
        <name_of_venv>         /home/usr/.local/share/jupyter/kernels/<name_of_venv>
   ```

   ###### Also, you can uninstall a kernel with:
   ```shell
    jupyter kernelspec uninstall <name_of_venv>
   ```

7.