+++
author = ""
date = 2019-10-08T18:30:00Z
description = ""
draft = true
image = "/uploads/2021/01/03/katna-1.png"
image_webp = "/uploads/2021/01/03/katna.png"
title = "Smart Image Cropping with katna"

+++
Some of the simple tasks for humans can be very tedious for machines. Image cropping is one of them. It's quite easy for human to identify the important area in a photo and decide the parts to retain or crop. But for machines, it is quite difficult.

[Katna](https://github.com/keplerlab/katna) is a python based open source smart image cropping tool that can intelligently identify important elements of an image and retain it during cropping. Katna content — aware algorithm can also retain important texts in the image.

![](/uploads/2021/01/03/katna_crop1.jpg)

![](/uploads/2021/01/03/katna_crop_2.png)

The best way to learn about Katna smart cropping module is to actually use it.

The best way to learn about Katna smart cropping module is to actually use it.

**Installation**

Katna can be installed either via PyPI or directly from source.

**_PyPI_ —** Installation via PyPI is pretty straight forward

* Install python 3
* Install with pip
```
    	pip install katna
```
**_Install from source_ —** Follow the steps below

* Install git.
* Install python 3.
* Clone the git repo.
```
    	git clone https://github.com/keplerlab/Katna.git
```
Change the current working directory to the folder where you have cloned Katna repo.
```
    cd <<path_to_the_folder_repo_cloned>>
```
If you use the anaconda python distribution then create a new conda environment. Keeping environment separate is a good practice.

```
    conda create --name katna python=3
    source activate katna
```
Run the setup
```
    python setup.py install
```