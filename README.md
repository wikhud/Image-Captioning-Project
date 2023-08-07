# ImageCaptioningProject
This code is based on https://github.com/keras-team/keras-io/blob/master/examples/vision/image_captioning.py, by A. K. Nain.

The model architecture is changed - now it doesn't consist of encoder-transformer. Instead, the decoder is more complex and uses 4 multihead attention layers with num_heads equals to 4.
The CNN model, for features extaraction, might now be selected from Inceptionv3, VGG16, ResNet50.
Metrics, such as BLEU, ROUGE, METEOR AND CIDEr are included. 
There were also some modifications made at data prepration step, to keep first 20 images and their coresponding captions (from Flickr8k dataset) out of training set.

This project was a part of my master thesis. The goal of this code was to select image captioning model with the best performance. The models were tested with different CNN models and different configurations of training parameters, such as: epochs, batch sizes and values of early stopping patience. The evalutaion based on metrics results and human judgement.

The best results were usually achieved by ResNet50, while Inceptionv3 mostly went the worst. VGG16 went pretty well. The modifications made to arhitecture usually didn't affect the final model performance - rearly, the results were better. Different combinations of training parameters didn't usually have great influence on it either. Only Inceptionv3 needed to have quite big batch size, otherswise the generated captions were just single repeated words, like "a man is is is is is is...".