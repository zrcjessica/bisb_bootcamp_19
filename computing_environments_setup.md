# Setting up your computing environments

Making sure our computing environments are up and running is essential to ensuring to optimizing your workflow! Here, I'll go over some essentials. 

* [Installing Anaconda](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#installing-anaconda)
	* [MacOS](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#macos)
	* [Windows](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#windows)
	* [Verify Installation](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#verify-installation)
	* [Uninstalling Anaconda](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#uninstalling-anaconda)
* [Jupyter Notebooks](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#jupyter-notebooks)
	* [Bash](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#bash)
	* [R](https://github.com/zrcjessica/bisb_bootcamp_19/blob/master/computing_environments_setup.md#r)

## Installing Anaconda
Anaconda is a popular distribution for Python and R, and widely used in many fields of scientific computing. Here, you can find instructions for installing Anaconda on your computer. 

### MacOS
Below are instructions for installing Anaconda for the command line on your Mac. They are essentially a summary of the instructions for the command-line install on the [official Anaconda docs](https://docs.anaconda.com/anaconda/install/mac-os/), so you can always refer to that link. Do NOT follow instructions for the graphical install! 

1. Download the **64-Bit Command Line Installer** for macOS [here](https://www.anaconda.com/distribution/#linux) for your desired Python version (personally, I use Python 3). You can click the link to automatically download the installer to your default downloads directory (`~/Downloads`) or right click on the installer link, copy the link address, and run `wget <paste copied link address>` in the Terminal in your desired download directory to download the installer. 

2. In the Terminal, navigate to the directory where the installer was downloaded. You should see a file whose name starts with `Anaconda3-` or `Anaconda2-`, depending on which Python version you chose to install, and which ends in the extension `.sh`. This is the Anaconda installer - it is a Bash file, and contains Unix commands for installation. You need to run this file with something along the lines of the following command:
```bash
bash ~/Downloads/Anaconda3-2019.07-MacOSX-x86_64.sh
```
Make sure to use the full path to the installer file - it may not be exactly the same as what I've pasted here (e.g. if you installed Python 2 or downloaded it to a different directory).

3. The installer will prompt you to review the license agreement, click `Enter` to view the license terms. Scroll to the bottom and enter `yes` to agree. 

4. The installer will prompt you to press `Enter` to confirm the location for the Anaconda installation. I suggest that you accept the default install location. Once you accept, the installer will display `PREFIX=/home/<user>/anaconda<2 or 3>`. This will be added to your `.bashrc` file. The installation will continue and this step will take a few minutes.

5. The installer should ask you "Do you wish the installer to initialize Anaconda<3 or 2> by running conda init?" I suggest you answer `yes`. 

6. You're done! The installer should print "Thank you for installing Anaconda!"

7. Close and reopen your Terminal window for the Anaconda installation to take effect. Alternatively, run the command: `source ~/.bashrc`.

### Windows

If you don't already have it installed, please make sure to install Windows Subsystem Linux. Instructions can be found [here](https://docs.microsoft.com/en-us/windows/wsl/install-win10). 

Once you have this installed, open a Bash terminal window. 

Note: when you open a new Bash environment, it will not automatically place you in your Windows system C:\ drive - instead, it places you in your UNIX account's home directory within the Linux subsystem's file system. In order to access your C:\ drive and all the files there, you have to navigate to the C:\ drive first, by running the following command:
``` bash
cd /mnt/c
```
WSL has access to your Windows filesystem. It's a good idea to create symlinks to your most-used Windows directories:
``` bash
ln -s /mnt/c/Users/ochapman/Documents $HOME/Documents
```
Below are instructions for installing Anaconda for the command line on your PC. They are essentially a summary of the instructions for the installation on the [official Anaconda docs](https://docs.anaconda.com/anaconda/install/linux/), so you can always refer to that link. 

1. Download the **64-Bit (x86) Linux Installer** for your desired Python version [here](https://www.anaconda.com/distribution/#linux). Even though you have a PC, don't download the Windows installer - you will be working in the command line, which runs on Linux. You can click the link to automatically download the installer to your default downloads directory (`~/Downloads`) or right click on the installer link, copy the link address, and run `wget <link address>` in the Terminal your desired download directory to download the installer. 

2. In your Bash terminal window, navigate to the directory where the installer was downloaded. You should see a file whose name starts with `Anaconda3-` or `Anaconda2-`, depending on which Python version you chose to install, and which ends in the extension `.sh`. This is the Anaconda installer - it is a bash file, and contains Unix commands for installation. You need to run this file with something along the lines of the following command:
```bash
bash ~/Downloads/Anaconda3-2019.07-MacOSX-x86_64.sh
```
Make sure to use the full path to the installer file - it may not be exactly the same as what I've pasted here (especially if you installed Python 2).

3. The installer will prompt you to review the license agreement, click `Enter` to view the license terms. Scroll to the bottom and enter `yes` to agree. 

4. The installer will prompt you to press `Enter` to confirm the location for the Anaconda installation. I suggest that you accept the default install location. Once you accept, the installer will display `PREFIX=/home/<user>/anaconda<2 or 3>`. This will be added to your `.bashrc` file. The installation will continue and this step will take a few minutes.

5. The installer should ask you "Do you wish the installer to initialize Anaconda<3 or 2> by running conda init?" I suggest you answer `yes`. 

6. You're done! The installer should print "Thank you for installing Anaconda!"

7. Close and reopen your Terminal window for the Anaconda installation to take effect. Alternatively, run the command: `source ~/.bashrc`.

### Verify Installation
Regardless of your OS, open your terminal window and use one of the following methods to verify your installation:
- Run the command `conda list`. If Anaconda is properly installed, this will display of list of installed packages and their versions.
- Run the python shell with the command `python`. If Anaconda is properly installed, the version information it displays on start up will include "Anaconda". To exit the python shell, run the command `quit()`, or `Ctrl+D`. 

### Uninstalling Anaconda
At some point in your life, Anaconda will probably break. When that happens, simply uninstall and reinstall Anaconda. [Here](https://docs.anaconda.com/anaconda/install/uninstall/) are instructions for uninstalling Anaconda properly. 

## Jupyter Notebooks
[Jupyter notebooks](https://jupyter.org/) are a useful web-app that allows you to do interactive computing in a number of different programming languages in your browser. It is very useful for data analysis, as it allows you to visualize your data as you go. They should be automatically installed along with Anaconda. You can try running it with the following command:
```bash
jupyter notebook
```
If you have a Mac, this command should automatically launch a new window or tab that displays all your folders and files in the directory from which you launched the command, and give you options to create new Jupyter notebooks or edit existing ones. 

If you have a PC, you will see a URL in your Terminal, which you should copy and paste into a new web browser window. This will launch Jupyter notebooks. 

By default, you should be able to Jupyter notebooks with the Python programming language. However, it might also be useful for you to install kernels for working in other languages. 

### Bash
Bash is the command language for working with the Unix shell. You can install a kernel that allows you to run Jupyter notebooks with Bash. To install, open your terminal and run the following commands:
```bash
pip install bash_kernel
python -m bash_kernel.install
```
More information [here](https://github.com/takluyver/bash_kernel).

### R
R already comes with its own graphical interface; however, it can also be useful to integrate R with Anaconda. You can find instructions on how to that [here](https://docs.anaconda.com/anaconda/user-guide/tasks/using-r-language/.) Start from **Creating an environment with R**. Once you do this, you can also install a kernel to use R with Jupyter notebooks. Instructions for doing so can be found [here](https://irkernel.github.io/installation/). **Do not install separate versions of R both within and outside conda, it will ruin your day.**


