# Semantic Segmentation

## Loading the Pretrained VGG16 Model

The pretrained model is loaded by [load_vgg()](main.py#L20-L42). It returns a tuple of the relevant layers which will be accessed later on.

## Feature Learning

The previously loaded layers are combined in a way suitable for semantic segmentation in [layers()](main.py#L46-L104). 

## Neural Network Optimization

Optimization of the trained network happens in [optimize()](main.py#L108-L135). This allows the inference stage to run faster, achieving good enough performance even on modest hardware.

## Training the Neural Network

The network is trained in [train_nn()](main.py#L139-L168). For each epoch its number is printed out and for each batch the loss is printed.

* The loss slowly decreases during training.
* I set the number of epochs to 25, loss didn't seem to decrease much further at that point.
* A batch size of 4 seemed to work fine, keeping memory usage low while still performing decently.
* Most of the road-pixels in the current lane are labeled as such, while everything else like trees, sky, other cars and asphalt outside the current lane are fairly clear. 

## Sample images
![um_000000.png](runs/1528105524.749326/um_000000.png  "um_000000.png")

![um_000001.png](runs/1528105524.749326/um_000001.png  "um_000001.png")

![um_000002.png](runs/1528105524.749326/um_000002.png  "um_000002.png")

![uu_000090.png](runs/1528105524.749326/uu_000090.png  "uu_000090.png")

![uu_000091.png](runs/1528105524.749326/uu_000091.png  "uu_000091.png")

![uu_000092.png](runs/1528105524.749326/uu_000092.png  "uu_000092.png")

As can be seen sections of well-lit road are handled well, while really dark shadows are more challenging to be properly classified as road.

All the images can be found in the [runs/1528105524.749326](runs/1528105524.749326) directory as well as in [project.zip](project.zip) if you want to view them in bulk.

## Original README
See [README-original.md](README-original.md)
