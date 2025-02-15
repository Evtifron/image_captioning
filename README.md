## Guys, training `.ipynb` file is `densenet161_lstm.ipynb`. You can look at this notebook and write your own model. Just enough to replace your model in this notebook and you can choose different parameters if you wish

# Steps
1. Clone this repository
```bash
$ git clone https://github.com/tojiboyevf/image_captioning.git
```

2. Move to project's directory and download dataset (Flickr8k) and GloVe
```bash
$ cd image_captioning
$ bash load_flickr8k.sh
$ bash load_glove.sh
```

# Instructions 

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://github.com/tojiboyevf/image_captioning/blob/main/densenet161_lstm.ipynb)


1. Download some MS COCO specific data from here: http://cocodataset.org/#download (described below)
 or run `load_coco.sh`

* Under **Annotations**, download:
  * **2014 Train/Val annotations [241MB]** (extract captions_train2014.json and captions_val2014.json, and place at locations cocoapi/annotations/captions_train2014.json and cocoapi/annotations/captions_val2014.json, respectively)  
  * **2014 Testing Image info [1MB]** (extract image_info_test2014.json and place at location cocoapi/annotations/image_info_test2014.json)

* Under **Images**, download:
  * **2014 Train images [83K/13GB]** (extract the train2014 folder and place at location cocoapi/images/train2014/)
  * **2014 Val images [41K/6GB]** (extract the val2014 folder and place at location cocoapi/images/val2014/)
  * **2014 Test images [41K/6GB]** (extract the test2014 folder and place at location cocoapi/images/test2014/)

# Environment
We use `conda` package manager to install required python packages. In order to improve speed and reliability of package version resolution it is advised to use `mamba-forge` ([installation](https://github.com/conda-forge/miniforge#mambaforge)) that works over `conda`. Once `mamba is installed`, run the following command (while in the root of the repository):
```
mamba env create -f environment.yml
```
This will create new environment named `img_caption` with many required packages already installed. You can install additional packages by running:
```
mamba install <package name>
```
You should run the following commands to install pytorch library:

```
conda activate img_caption
```

```
conda install pytorch torchvision torchaudio cudatoolkit=11.3 -c pytorch
```

```
conda install -c pytorch torchtext
```

In order to read and run `Jupyter Notebooks` you may follow either of two options:
1. [*recommended*] using notebook-compatibility features of modern IDEs, e.g. via `python` and `jupyter` extensions of [VS Code](https://code.visualstudio.com/).
2. install jupyter notebook packages:
  either with `mamba install jupyterlab` or with `mamba install jupyter notebook`

*Note*: If you prefer to use `conda`, just replace `mamba` commands with `conda`, e.g. instead of `mamba install` use `conda install`.
