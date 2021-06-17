---
layout: post
title:  "Working with Anaconda!"
date:   2021-06-08 05:38:32 +0530
categories: jekyll update
---

I am learning to work with Nbdev. 

One of the requirement is to install Anaconda and run nbdev library from the save server where Jupyter Notebook is running. 

Uptill now I utilised Google Colab or Paperspace Code for most of my work. 

However, here it required installing Anaconda, and I followed the documentation available on the site as it is. 

<h6>Helpful resources: </h6>

[Anaconda Cheetsheat](https://kapeli.com/cheat_sheets/Conda.docset/Contents/Resources/Documents/index)

To come out of Conda completely: <em>conda deactivate</em>

[Markdown Resource](https://www.markdownguide.org/basic-syntax/) As I am learning Markdown by doing


Learning how can I add packages to a specific environment in conda only?

Anaconda Navigator help me to easily install Jupyter Notebook to Python 3.7 environment. However, I did read that if I activate an environment and install packages. The packages form part of that environment only. 

I will check this will installing Nbdev


1-> Copyright issue

2-> [On Ubuntu 20.10 and latest version of Windows 10, Anaconda installs nbdev-0.2.40 when the conda install -c fastai nbdev command is used per the Tutorial's instructions. When the nbdev_build_lib command is issued, it fails with an error on the "docs/_data/topnav.yml" file. To fix this (on Ubuntu), I had to force Anaconda to upgrade to the latest version of nbdev (1.1.13) with this command: conda upgrade -c fastai nbdev. I suspect this will also fix things on Windows 10, too. You may wish to consider mentioning this in your docs. An earlier reported issue, with the same problem, solved this by using pip instead on conda, but the conda upgrade command did the trick for me.](https://github.com/fastai/nbdev/issues/451)

