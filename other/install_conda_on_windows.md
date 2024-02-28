---
created: 2024-02-22T13:11:50 (UTC -07:00)
tags: []
source: https://bootcampspot.instructure.com/courses/5432/pages/1-getting-started?module_item_id=1200073
author: 
---

# 1: Getting Started: Bootcamp: DU-VIRT-AI-PT-02-2024-U-LOLC-MTTH

> ## Excerpt
> Install the following tools before your first class this week.

---
Install the following tools before your first class this week.

Don’t worry if you encounter any issues during setup. Your instructional staff will help you troubleshoot any errors and answer your questions on the first day of class.

### Anaconda Package Manager

The Anaconda package manager is a free and open-source tool that helps you manage all the different software packages you need for coding in data science and AI. It simplifies package management and deployment by providing a curated collection of over 1,500+ data science packages. This is especially helfpul for developers in AI because it keeps all the complex tools they need in one place, ready to use, which saves time and avoids the hassle of managing those tools individually.

### Installing and Configuring Your Anaconda Environment

This section reviews the installation and configuration process for your Anaconda environment, which consists of the following steps:

1.  Download and install Anaconda for Python 3.
    
2.  Configure the Anaconda `dev` virtual environment.
    
3.  Activate the Anaconda `dev` environment.
    

**important**

In this course, we will create and use a virtual environment that uses Python 3.10. Be sure to follow our instructions for creating the virtual environment and activate the environment before you run any code.

### Download and Install Anaconda

This section reviews the steps to download and install Anaconda.

**important**

We recommend having the Anaconda installation [documentation Links to an external site.](https://docs.anaconda.com/anaconda/install/) available as you work through the installation process, just in case any issues arise that you need to troubleshoot.

1.  Navigate to the Anaconda download site, which can be found [here Links to an external site.](https://www.anaconda.com/data-science-platform). Click the "Free Download" button, as shown in the following image, or scroll down to the Anaconda Installers:
    
    ![A screenshot shows the Download button.](imgs/install_conda_windows/anaconda-download.png)
    
2.  On the Anaconda Installers section of the page, select the appropriate distribution for your system.
    
    ![A screenshot shows the Anaconda installation options.](imgs/install_conda_windows/anaconda-version-download.png)
    
3.  When prompted to do so, save the installer. After the download is complete, run the download file. This will launch an installation wizard that will take you through the Anaconda installation. Continue through the installation process by clicking either "I Agree" or "Continue."
    
    ![A screenshot shows the installation wizard and Continue button.](imgs/install_conda_windows/anaconda-begin-install.png)
    
4.  For Windows users, you will eventually get to a screen that asks if you would like to set your PATH environment variable by using the installation wizard. DO check this box. Another box will ask if you would like to clear the package cache upon completion. DO check this box as well. Make sure that all boxes are checked, as shown in the following screenshot. Then, click Install.
    

**note**

Even though Anaconda does not recommend adding to PATH, as it could conflict with other Python installations, Anaconda will be our primary Python distribution.

![A screenshot shows the installation wizard and Install button.](imgs/install_conda_windows/anaconda-windows-install-path-2.png)

5.  Click Finish once the installation is complete.

### Check Your Anaconda Installation

#### MacOS

As a best practice, you should always check the version of the software you installed and confirm that it's installed correctly. Let's take care of this now for Anaconda.

Open the command line and run the command `conda --version`. If the command line returns `conda 22.9.0` or later, the software is installed correctly.

You need to type "conda" and not "anaconda" because Anaconda packages are managed by the package management system "conda." Anaconda is the distribution management system.

Note that package versions change often, so you may need to update the packages managed by conda. To find out what version of conda you have on your computer, type and run `conda --version` in the command line. If the command line returns `conda 22.9.0` or later, you should have the latest version of conda.

#### Windows

On Windows, we can do this using the Anaconda prompt.

**note**

On Windows 10, to find the application you want to open, type the name in the search bar.

In the search bar, type "Anaconda Prompt."

![Typing and selecting Anaconda Prompt in the search menu on Windows 10.](imgs/install_conda_windows/data-4-1-1-anaconda-prompt-search.png)

The Anaconda prompt should look like the following:

```shell
(base) C:\Users\your_home_directory>
```

After the prompt, `>`, type and run `conda --version`. If the prompt returns `conda 22.9.0` or later, the software is installed correctly.

You need to type "conda" and not "anaconda" because Anaconda packages are managed by the package management system "conda." Anaconda is the distribution management system.

Note that package versions change often, so you may need to update the packages managed by conda. To find out what version of conda you have on your computer, type and run `conda --version` in the command line. If the command line returns `conda 22.9.0` or later, you should have the latest version of conda.

If you need to get the latest version of conda and other packages, perform the following steps (these steps are the same for both macOS and Windows):

1.  Type and run `conda update conda` to update the packages distributed by Anaconda.
    
2.  Run `conda--version` to check if conda was updated.
    

### Setting Up Your Anaconda Environment

These instructions will be performed in your live class time; they are listed here as a reference only. You do not need to complete these steps before class.

1.  Open Terminal (Mac) or Git Bash (Windows).
    
    -   Mac users can find Terminal by opening their Spotlight Search and typing “terminal”.
        
    -   Windows users can open Git Bash by locating it in their Start Menu.
        
2.  Enable the Terminal commands by following the instructions for your operating system.
    
    -   **Windows:** In your Terminal, run the command `conda init bash`. Then close your Terminal and start a new one.
        
    -   **Mac:** If you're running an OS version earlier than 10.15 OR running version 10.15 with a `bash` terminal environment, type `conda init bash`. If you're running versions 10.15 (Catalina) or later AND running the `zsh` environment, type `conda init zsh`. Then close your Terminal and start a new one.
        
3.  First, update the conda base environment:
    

```
conda deactivate
conda update conda
conda update anaconda
conda update -n base -c defaults conda
```

-   Type `y` whenever prompted to proceed.

4.  Next, create a new environment called `dev` using Python 3.10 with the default packages from Anaconda:

```
conda create -n dev python=3.10 anaconda -y
```

**note**

Anaconda allows you to create multiple virtual environments with different versions of Python. In this course we will use Python version 3.10. **Create the virtual environment as indicated using the _`python=3.10`_ parameter and activate it prior to running your code.** If you run into any issues with Python 3.10, you can always create a new virtual environment that uses a different Python version.

5.  To activate your environment, enter `conda activate dev`.
    
6.  Verify the installations by executing the `conda list` command and then locating the following packages in the populated list:
    
    -   Numpy
        
    -   Pandas
        
    -   Matplotlib
        
7.  Though it will rarely be necessary, you can exit the environment by entering `conda deactivate`.
    

**note**

Whenever you open a new GitBash or Terminal window, remember to start by activating your environment.
