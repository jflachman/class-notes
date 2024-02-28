Thanks everyone for commenting/contributing! I made this in college for a class and I no longer really use the technology. I encourage you all to help each other, but I probably won't be answering questions anymore.

This article is also on my blog: https://emilykauffman.com/blog/install-anaconda-on-wsl 

**Note**: `$` denotes the start of a command. Don't actually type this.

# Steps to Install Anaconda on Windows Ubuntu Terminal
1. Install WSL (Ubuntu for Windows - can be found in Windows Store). I recommend the latest version (I'm using 18.04) because there are some bugs they worked out during 14/16 (https://github.com/Microsoft/WSL/issues/785)
2. Go to https://repo.continuum.io/archive to find the list of Anaconda releases
3. Select the release you want. I have a 64-bit computer, so I chose the latest release ending in `x86_64.sh`. If I had a 32-bit computer, I'd select the `x86.sh` version. If you accidentally try to install the wrong one, you'll get a warning in the terminal. I chose `Anaconda3-5.2.0-Linux-x86_64.sh`.
4. From the terminal run `wget https://repo.continuum.io/archive/[YOUR VERSION]`. Example: `$ wget https://repo.continuum.io/archive/Anaconda3-5.2.0-Linux-x86_64.sh`
5. Run the installation script: `$ bash Anaconda[YOUR VERSION].sh` (`$ bash Anaconda3-5.2.0-Linux-x86_64.sh`)
6. Read the license agreement and follow the prompts to accept. When asks you if you'd like the installer to prepend it to the path, say yes.
7. Optionally install VS Code when prompted (some have reported this installation doesn't work - checkout https://gist.github.com/kauffmanes/5e74916617f9993bc3479f401dfec7da#gistcomment-3665550)
8. Close the terminal and reopen it to reload .bash configs.
9. To test that it worked, run `$ which python`. It should print a path that has anaconda in it. Mine is `/home/kauff/anaconda3/bin/python`. If it doesn't have anaconda in the path, do the next step. Otherwise, move to step 11.
10. Manually add the Anaconda bin folder to your PATH. To do this, I added "export PATH=/home/kauff/anaconda3/bin:$PATH" to the bottom of my ~/.bashrc file. 
11. To open jupyter, type `$ jupyter notebook --no-browser`. The no browser flag will still run Jupyter on port 8888, but it won't pop it open automatically. it's necessary since you don't have a browser (probably) in your subsystem. In the terminal, it will give you a link to paste into your browser. If it worked, you should see your notebooks!

Leave a comment on anything you see that doesn't work and I can look into it!


## A few other things that I did out of laziness but aren't necessary
- made a symlink between my C:/Users/kauff/Documents/JupyterNotebooks folder (where I put my downloaded notebooks in Windows) to my Ubuntu notebook directory:
In the WSL terminal:
1. `cd ~`
2. `ln -s /mnt/c/Users/kauff/Documents/JupyterNotebooks/ notebooks` Now when you look at Jupyter on :8888, you should see a notebooks folder that has everything your C:/Users/kauff folder has.
3. I made an alias for the juypter command by putting this command in my .bash_aliases: `alias jup='cd /home/kauff/notebooks && jupyter notebook --no-browser`. Restart the terminal for this new command to take effect.
4. To test, simply type `jup` from anywhere in the ubuntu directory and it will take you notebooks folder and run jupyter. When you copy and paste the URL, you'll see everything in your C:/Users/kauff/JupyterNotebooks folder.

## Troubleshooting
Thanks to Alexander for the tip:
"A note to be made from my installation -- there was an issue with Jupyter that required `conda update conda` and `conda update conda-build`. I then uninstalled/reinstalled jupyter with conda to avoid a 500 error for dependencies".

## Sources
https://conda.io/docs/glossary.html#anaconda-glossary
https://www.cgranade.com/blog/2016/08/22/qutip-on-wsl.html
https://jupyter.readthedocs.io/en/latest/install.html
