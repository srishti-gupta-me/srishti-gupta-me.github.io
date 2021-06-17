---
layout: post
title:  "Working with Anaconda!"
date:   2021-06-08 05:38:32 +0530
categories: jekyll update
---

I am learning to work with [Nbdev](https://nbdev.fast.ai/). 

One of the requirement is to install Anaconda and run nbdev library from the same server where Jupyter Notebook is running. 

Uptill now I utilised Google Colab or Paperspace Code for most of my work. 

However, here it required installing Anaconda, and I followed the documentation available on the site as it is. Without any issues. 

<h6>Helpful resources: </h6>

[Anaconda Cheetsheat](https://kapeli.com/cheat_sheets/Conda.docset/Contents/Resources/Documents/index)

I learnt that nbdev library was test to work on Python 3.7 and hence I needed Python 3.7 instead of 3.8 (also I was running through some errors and while searching for solutions I found it is easier to try with Python 3.7). This is where Anaconda is helful, you can create environments and I wanted to keep Python3.7 and Nbdev in one environment isolated. 

The above cheat sheet, consists of command on how to create environments and activate and dectivate them. 

**To come out of Conda completely: <em>conda deactivate</em>**

[Markdown Resource](https://www.markdownguide.org/basic-syntax/) As I am learning Markdown by doing


Learning how can I add packages to a specific environment in conda only?

By now I had setup a Python 3.7 environment but when I was installing Nbdev library, for some reason it was available globally. This is when I went back to [Anaconda Documentation page](https://docs.anaconda.com/anaconda/). 

How I knew it was available globally? 
I could access the nbdev library from the (base) enviroment as well.

On the docs page, I learnt about Anaconda Navigator which is a GUI and help me visualize which environment has what packages and libraries installed. Anaconda Navigator also makes it easy installing libraries to environments. For example, Jupyter Notebook is installed during Anaconda installation but is available in the base environment only. When a new enviroment is created it has to be added separately. 

**Issues I faced during working with Nbdev tutorial:**

1-> Settings.ini need to be updated with Copyright field, solution that worked was <em>copying author name</em> here.  

2-> [On Ubuntu 20.10 and latest version of Windows 10, Anaconda installs nbdev-0.2.40 when the conda install -c fastai nbdev command is used per the Tutorial's instructions. When the nbdev_build_lib command is issued, it fails with an error on the "docs/_data/topnav.yml" file. To fix this (on Ubuntu), I had to force Anaconda to upgrade to the latest version of nbdev (1.1.13) with this command: conda upgrade -c fastai nbdev. I suspect this will also fix things on Windows 10, too. You may wish to consider mentioning this in your docs. An earlier reported issue, with the same problem, solved this by using pip instead on conda, but the conda upgrade command did the trick for me.](https://github.com/fastai/nbdev/issues/451)

