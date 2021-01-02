# Analyzing-Facebook-DETR-Transformers
Note: Kinldy note that it is just an experimental mini project. We tried to work with Facebook's newly introduced algorithm DETR. The code and model are mostly Facebook's with small modifications from our side.
<br />
Facebook’s detection transformer (DETR) algorithm uses transformers for the task of object detection. It
uses Convolutional Neural Network in its initial stages before passing the feature maps to the
transformer. DETR consists of simpler and flexible pipeline architecture.
The Convolutional Neural Network (CNN) extracts the local information and feature maps from the input
images and obtains a multi-channel higher-order representation of the image. The set of image features
are converted into a vector form in order to facilitate the parallel transmission of the image features.
The transformer consists of the encoder and decoder setup as discussed above. The encoder takes the
one dimensional feature map and outputs the N number of fixed length vectors where N is the number
of objects in the image presumed by the model.
The decoder decodes the embeddings in the form of a bounding box coordinates using the mechanism
of attention (refer to the famous paper "Attention is all you need"). This information is then fed into a feed-forward neural network
which predicts the normalized center coordinates, length and breadth of the bounding box and the
linear layer makes a prediction of the class label using a softmax function. 
The DETR architecture consists of set-based global loss which forces unique predictions using bipartite
matching loss. For a fixed small set of learned object queries, DETR evaluates the relations of the objects
and the global image context to directly output the final set of predictions in parallel.
![alt text](https://github.com/MursalinLarik/Analyzing-Facebook-DETR-Transformers-/blob/main/architecture.png)
<br />
<br />
Using this architecture we were able to analyse its performance on several scenarios. The results are as following:
![alt text](https://github.com/MursalinLarik/Analyzing-Facebook-DETR-Transformers-/blob/main/panoptic1.png)
![alt text](https://github.com/MursalinLarik/Analyzing-Facebook-DETR-Transformers-/blob/main/pan2.png)
![alt text](https://github.com/MursalinLarik/Analyzing-Facebook-DETR-Transformers-/blob/main/pan3.png)
![alt text](https://github.com/MursalinLarik/Analyzing-Facebook-DETR-Transformers-/blob/main/pan4.png)
![alt text](https://github.com/MursalinLarik/Analyzing-Facebook-DETR-Transformers-/blob/main/obj_det.png)
