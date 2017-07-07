# Melanoma Cancer Detection

## Download the ISIC Data Set
1) Use [ISIC-Dataset-Downloader](https://github.com/vgupta-ai/ISIC-Dataset-Downloader) to download the ISIC data set.
```bash
$ git clone https://github.com/vgupta-ai/ISIC-Dataset-Downloader.git
$ cd ISIC-Dataset-Downloader
$ python downloadImageMetaData.py
$ python downloadImages.py
```

2) Combine images across different sources
```bash
$ mkdir -p melanoma-dataset/benign
$ mkdir -p melanoma-dataset/malignant
$ mv ISIC-Dataset-Downloader/*/benign/* melanoma-dataset/benign/
$ mv ISIC-Dataset-Downloader/*/malignant/* melanoma-dataset/malignant/
```

3) Delete all the checkpoints from the "model" directory before training a new model from scratch.

4) Run the following command. This will read all the images from the dataset folder and split them into training and testing set and pickle them. This is done to avoid loading the images multiple times, so skip this step if you have already done this before.
```python
python prepareDataSetFromImages.py 
```

5) Run the following command to train the models. 
```python
python convNetTrain.py
```

6) Run the following command to test the model.
```python
python convNetTest.py 
```

The file <b> config.py </b> contains the various parameters/flags that can be set.
