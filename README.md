# Working with Python Environments

# Table of Contents
1. [Windows](##Windows)
2. [Linux](##Linux)
3. [Conda*](##Conda)

Recommended*

## Windows

### How to install Python

You can download it from the [official page](https://www.python.org/downloads/).

![](images/image1.png?raw=true)

Execute the downloaded file in order to install Python; then, follow the wizard. Make sure we select the option **Add Python 3.8 to PATH**; as a result, we won't have to configure Python in our PATH manually.

![](images/image2.png?raw=true)

Press **Install Now** and wait.

![](images/image3.png?raw=true)

After the installation is complete, we can exit the wizard by pressing **Close**.

Afterwards, we can open some CLI, like CMD or PowerShell, and check our Python version:

```powershell
> py --version
Python 3.8.4
```

This should prompt the version of Python we previously downloaded and installed. In case the command doesn't work, it is recommended to reboot the CLI or the whole system; thus, the PATH configuration can be refreshed.

### Configuring a Virtual Environment

We will take advantage of the tool **venv**, which is a standard Python library since version 3.3.

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
