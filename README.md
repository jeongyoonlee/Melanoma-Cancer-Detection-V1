# Melanoma Cancer Detection

## Download the ISIC Data Set
* Use [ISIC-Dataset-Downloader](https://github.com/vgupta-ai/ISIC-Dataset-Downloader) to download the ISIC data set.
```bash
$ git clone https://github.com/vgupta-ai/ISIC-Dataset-Downloader.git
$ cd ISIC-Dataset-Downloader
$ python downloadImageMetaData.py
$ python downloadImages.py
```

* Combine images across different sources
```bash
$ mkdir -p melanoma-dataset/benign
$ mkdir -p melanoma-dataset/malignant
$ mv ISIC-Dataset-Downloader/*/benign/* melanoma-dataset/benign/
$ mv ISIC-Dataset-Downloader/*/malignant/* melanoma-dataset/malignant/
```

## Train a Melanoma Cancer Classification Model
* Set parameters and flags in `config.py`.

* To train a new model, delete checkpoints in the `model` directory.

* Load images, split them into training and test sets and pickle them.
```python
python prepareDataSetFromImages.py 
```

* Train the model.
```python
python convNetTrain.py
```

## Test the Model with the Hold-Out Test Set.
* Test the model.
```python
python convNetTest.py 
```
