# Computer Vision - MAIBI

This repository contains the notebooks for the course of Computer Vision, given 
at the master AI for Business and Industry.

# Setting up VSC OnDemand

- Browse to <https://ondemand.hpc.kuleuven.be/> and log in
- Click on *Login Server Shell Access*
- Test if Conda is installed by running `conda --version`. If this runs without an error message containing something like `command not found`, Conda is installed.
- If you do get a `command not found` error, you can install Conda as follows:

```bash
wget https://repo.anaconda.com/miniconda/Miniconda3-py310_24.1.2-0-Linux-x86_64.sh
bash Miniconda3-py310_24.1.2-0-Linux-x86_64.sh -b -p $VSC_DATA/miniconda3
echo 'export PATH="${VSC_DATA}/miniconda3/bin:${PATH}"' >> ~/.bashrc
source ~/.bashrc
```

- Run the following commands:

```bash
cd $VSC_DATA
git clone https://github.com/florisdf/maibi_cv.git
cd maibi_cv
conda create -n maibi_cv python=3.10
source activate maibi_cv
pip install -r requirements.txt --no-cache-dir
python -m ipykernel install --prefix=${VSC_HOME}/.local --name maibi_cv
```

- Go back to <https://ondemand.hpc.kuleuven.be/>
- Click on *Jupyter Lab*
- Fill in the fields:
    - Partition: *interactive*
    - Number of hours: *4* (can have a value up to *16*)
    - Number of nodes: *1*
    - Required memory per core in megabytes: *3400*
    - The *Number of cores* and *Number of gpu's* depend on the notebooks you'll be running. For simple notebooks, 1 core will suffice and you won't need any GPUs. For notebooks in which we you train a neural network, try 4 cores and 1 GPU.
- Click *Launch*
- Once Jupyter is running, click *Connect to Jupyter Lab*

# Getting started on your own pc

## Install Python and pip

If this is not yes installed, see <https://www.python.org/downloads/> for
instructions.

Also, make sure pip is installed. See
<https://pip.pypa.io/en/stable/installation/> for details.

## Set up the virtual environment

Open a terminal window and clone this repository

```bash
git clone https://github.com/florisdf/maibi_cv.git
```

Change the directory of your terminal to move into the repository.

```bash
cd maibi_cv
```

Create a new virtual environment.

```bash
python -m venv .venv
```

Activate the environment you just created:

```bash
source .venv/bin/activate

.venv\Scripts\activate (windows)
```

Also, make sure pip has the most recent version.

```bash
pip install --upgrade pip
```

Finally, install the requirements into the virtual environment.

```bash
pip install -r requirements.txt
```

## Open Jupyter Notebook

Run the following command in your terminal. **Make sure that**:

1. You are in the directory of this repository (so in the directory called
   `maibi_cv`).
2. You have **activated the virtual environment** with `source .venv/bin/activate`.

```bash
jupyter notebook
```
