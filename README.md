# Working with Python Environments

When working on Python projects, it is important to manage isolated "environments"; preferably one for each individual project. Thus, we can avoid conflicts on package versioning among projects, as they will have different dependencies.

# Table of Contents
1. [Windows](#Windows)
2. [Linux](#Linux)
3. [Conda*](#Conda)

Recommended*

## Windows

### How to Install Python

You can download it from the [official page](https://www.python.org/downloads/).

![](images/image1.png?raw=true)

Execute the downloaded file in order to install Python; then, follow the wizard. Make sure we select the option **Add Python 3.8 to PATH**; as a result, we won't have to configure Python in our PATH manually.

![](images/image2.png?raw=true)

Press **Install Now** and wait.

![](images/image3.png?raw=true)

After the installation completes, we can exit the wizard by pressing **Close**.

Afterwards, we can open some CLI, like CMD or PowerShell, and check our Python version:

```powershell
> py --version
Python 3.8.4
```

This should prompt the version of Python we previously downloaded and installed. In case the command doesn't work, it is recommended to reboot the CLI or the whole system; thus, the PATH configuration can be refreshed.

### Configuring a Virtual Environment

In this case, we will take advantage of the tool **venv**, which is a standard Python library since version 3.3.

Let's create first a folder, and then a virtual environment named *env-project*:

```bash
PS> mkdir folder-project
PS> cd folder-project
PS> py -m venv env-project
```

This command will create a new folder, which will contain all the files for the virtual environment.

### Activate the Virtual Environment

Execute the file **activate** inside the folder named **Scripts**, which has been generated along with the virtual environment:

```bash
PS> .\env-project\Scripts\activate
```

> Notice that the character **\\** is used when moving across folders in Windows, instead of **/** which is used in Linux systems.

Then, we can easily confirm we are inside our virtual environment, as the prompt will be added a prefix with its name:

```bash
(env-project) PS>
```

Also, we can verify that the virtual environment's path is set for the Python interpreter:

```bash
(env-project) PS> where python
./env-project/Scripts/python.exe
```

### Deactivate the Virtual Environment

When we don't need to work over the virtual environment anymore, we must deactivate it:

```bash
(env-project) PS> deactivate
```

## Linux

### How to Install Python

By default, most of the Linux distributions already have Python3 installed; you can verify this by typing:

```bash
$ python3 --version
```

On the contrary, you can install it as follows:

```bash
$ sudo apt install software-properties-common
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt update
$ sudo apt install python3.8
```

In case you are working on **macOS**, you must first install *homebrew*:

```bash
$ /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Then:

```bash
$ brew install python3
```

We will also need *pip*, which comes with Python3 by default; you can check this by typing:

```bash
$ pip --version
```
By contrast, you can also install it:

```bash
$ sudo apt install python3-pip
```

### Configuring the Virtual Environment

Let's create first a folder, and then a virtual environment named *env-project*:

```bash
$ mkdir folder-project
$ cd folder-project
$ python3 -m venv env-project
```

### Activate the Virtual Environment

Execute the file activate inside the folder named **bin**, which has been generated along with the virtual environment:

```bash
$ source env-project/bin/activate
```

We can verify that the virtual environment's path is set for the Python interpreter:

```bash
$ which python
../env-project/bin/python
```

### Deactivate the Virtual Environment

When we don't need to work over the virtual environment anymore, we must deactivate it:

```bash
$ deactivate
```

## Conda

We can also use [Anaconda](https://www.anaconda.com/), which is an open source ecosystem for working with Python and other related tools such as Jupyter Notebook.

### Download and Installation

Go to [Anaconda Individual Edition page](https://www.anaconda.com/products/individual); then, search for the Anaconda Installers section. Once there, choose the installer according to your operating system and machine specifications.

These are the most common selections:

![](images/anaconda_installers.png?raw=true)

Download it and perform the installation process on your system.

**Once completed, you can check your installation as follows:**

#### Windows

Search for the Anaconda Prompt from the system menu:

![](images/verify_windows_1.png?raw=true)

Open it, and then type `conda --version`.

You should see the anaconda version installed printed. For example:

```powershell
(base) > conda --version
Conda 4.10.3
```

*You can also type `conda info` to see more information, including the Python version installed.*

#### Linux or macOS

Open a terminal and type either `conda --version` or `conda info`.

### Create a Virtual Environment

By default, we are given a conda environment named **base**:

```bash
(base) > 
```

We can create a new virtual environment by typing:

```bash
(base) > conda create -n env-project
```

You can also set a specific Python version (or any other package you will need):

```bash
(base) > conda create -n env-project python=3.8
```

Then, you can check the list of available Conda environments with:

```cmd
(base) > conda env list
# conda environments:
#
base                  *  C:\User\anaconda3
env-project              C:\User\anaconda3\envs\env-project
```

### Activate a Virtual Environment

```bash
(base) > conda activate env-project
```
Next, you will see how the prefix prompt is replaced to indicate you are working now on the chosen environment:

```bash
(env-project) > 
```

### Deactivate a Virtual Environment

```bash
(env-project) > conda deactivate
```

As a result, you will be set back to the default conda environment:

```bash
(base) > 
```
