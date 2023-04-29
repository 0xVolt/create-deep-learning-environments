# Getting started with Jupyter Lab for Deep Learning

## Steps
These are the steps to initialise a virtual environment for every deep learning project. They're as follows:
1. Set the `conda` environment to `base` so you can launch Jupyter Lab

2. `cd` into the directory you're working in

3. Create a Python `venv` with the command:
   ```shell
    python3 -m venv <name_of_venv>
   ```

4. Activate the `venv` with the command:
   ```shell
    source <name_of_venv>/bin/activate
   ```

   You can deactivate the `venv` when you're done with the project with:
   ```shell
    deactivate
   ```


5. Install `ipykernel` to link our `venv` with a Jupyter kernel (which is another word for environment or runtime). **This is a one-time installation**. We do this with:
   ```shell
   pip install ipykernel
   ```
   ###### *Note: You can list out all the libraries installed with the command:*
   ```shell
   pip list
   ```

6. Link the kernel with the Jupyter Lab runtime using:
   ```shell
   python3 -m ipykernel install --user --name=<name_of_venv>
   ```

   When the command-line outputs,
   ```shell
    Installed kernelspec ImageClassification in /home/usr/.local/share/jupyter/kernels/<name_of_venv>
   ```
   **You know you're on the right track.**

7.