# Image Captioning Project
This code is based on https://github.com/keras-team/keras-io/blob/master/examples/vision/image_captioning.py, by A. K. Nain.

The model architecture was changed - encoder has been removed. Instead, the decoder got more complex and now consists of 4 multihead attention layers and 4 heads.
The CNN model, for features extaraction, can be now selected from: Inceptionv3, VGG16 or ResNet50.
Metrics, such as BLEU, ROUGE, METEOR AND CIDEr were included. 
Some modifications have been made at data prepration step to keep first 20 images and their coresponding captions (from Flickr8k dataset) out of training set.

This project was a part of my master thesis. The goal was to select image captioning model with the best performance. The models were tested with different CNN models and different configurations of training parameters, such as: num of epochs, batch sizes and values of early stopping patience. The evalutaion based on metrics results and human judgement.

The best results were usually achieved with ResNet50, while Inceptionv3 mostly went the worst. VGG16 went pretty well. The modifications made to arhitecture usually didn't affect the final model performance - rearly, the results were better. Different combinations of training parameters didn't have a substantial impact either. Only Inceptionv3 needed a bigger batch size, otherswise, the generated captions were just single repeated words, like "a man is is is is is is...".

An example code output for an image of Flickr8k dataset:



![Zrzut ekranu 20237](https://github.com/wikhud/Image-Captioning-Project/assets/99511332/f60aec53-1369-4456-9112-c5e96d8f8efd)





*Please, excuse my mistake in "Predicted caption: ".
