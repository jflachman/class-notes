---
created: 2024-02-22T13:10:04 (UTC -07:00)
tags: []
source: https://bootcampspot.instructure.com/courses/5432/pages/2-getting-started?module_item_id=1200125
author: 
---

# Create a Conda Environment

Anaconda is required to begin this module. You should already have installed Anaconda in Module 1, but if you missed that installation, refer back to the Module 1 Getting Started page.

### Activate Your Environment

Remember to activate your `dev` environment prior to running any Python code.

1.  Open Terminal on macOS or Anaconda Prompt on Windows and then run the following command:
    
    `conda activate dev`
    
2.  When `(dev)$` appears, you’re in the Conda environment.
    

### Running Python Code

During class this week, you will be learning how to write and run Python code. There are various methods that will be demonstrated, and you may use the following instructions to remind you how to access these methods.

#### Using the Python Command Line Interpreter (CLI)

The Python CLI will allow you to run Python code directly from the command line, executing the code once a line of code (or code block) is terminated. You cannot run Python scripts (.py files) from the CLI, but it is useful for testing excerpts of code to ensure it runs as expected.

To launch the Python command line interpreter:

1.  Launch Terminal for macOS or Anaconda Prompt for Windows.
    
2.  Make sure you are in your `dev` environment.
    
3.  Type `python` or `python3` and press Enter.
    

You will know the Python interpreter is running when you see the following in your Terminal window:

`>>>`

To exit the Python interpreter:

1.  Type `exit()` or `quit()` and press Enter.

#### Running a Python Script from the Command Line

To run a Python script from the command line:

1.  Launch Terminal for macOS or Anaconda Prompt for Windows.
    
2.  Make sure you are in your `dev` environment.
    
3.  Within your terminal, navigate to the folder the script is located in.
    
4.  Type `python script_name.py` (where script\_name.py is the name of the Python script) and press Enter. This will launch the script.
    

In the event that you have created a script with no exit (for example, you have a continuous loop with no way to exit it), you may need to interrupt the script to exit. The keyboard interrupt command is different depending on your operating system.

For Windows, type CTRL+C.

For macOS, type CTRL+D.

#### Running Python from VS Code

VS Code has an inbuilt Terminal that allows you to run Python code within the program, rather than having to switch to the Terminal in macOS, or Git Bash or Anaconda Prompt in Windows.

Activate your Anaconda environment in VS Code:

1.  Open a Python script in VS Code.
    
2.  In the footer of the VS Code window, you should see the word "Python". The numbers to the right of this indicate the Python version you are using. Click on those numbers to bring up the menu to change the Python interpreter.
    
3.  Select your `dev` environment.
    

![A screenshot of the Select Python Interpreter menu in VS Code.](imgs/condaenv/select-interpreter-annotated.png)

To use the VS Code Terminal:

1.  Open your Python script in VS Code.
    
2.  Right click anywhere in the Python script file. This will pull up a menu.
    
3.  Hover your mouse over the "Run Python" option. This will bring up two choices:
    
    -   Select "Run Python in Terminal" if you want to run the entire script.
        
    -   "Run Selection/Line in Python Terminal" will execute the line you are on when you right-clicked, or if you've highlighted a section of code in the script, it will execute that selection.
        

If you run into any problems with any of these instructions, you may request a Tutor for assistance, or attend Office Hours to get help from your instructor and/or TA(s).
