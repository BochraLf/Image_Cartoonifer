# Image_Cartoonifer

### Image processing Project : Transform images into its cartoon.
We will CARTOONIFY the images. Thus, we will build a python application that will
transform an image into its cartoon using OpenCV.
#### Workflow:
To convert an image to a cartoon, multiple transformations are done. Firstly, an image
is converted to a Grayscale image, similar to the old day’s pictures! Then, the
Grayscale image is enhanced using histogram equalization, then it will be
smoothened, and we try to extract the edges in the image. Finally, we form an image
and mask it with edges. This creates a beautiful cartoon image.
- Step 1: Importing the required modules
- Step 2: Contrast improvement ( to make details of the image stand out )
- Step 3: To smoothen an image, we simply apply a blur effect. ( I tried with different
filters just to see the results, but there wasn't that big difference)
- Step 4: Edges, we will try to retrieve the edges and highlight them. This is attained by
the adaptive thresholding technique. The threshold value is the mean of the
neighborhood pixel values area minus the constant C. C is a constant that is
subtracted from the mean or weighted sum of the neighborhood pixels
- Step 5: MASKING, we perform bitwise and on two images to mask them.
- Step 6: Now with the aesthetic, black_and_white_aesthetic will be created with
normal thresholding technique, so the threshold may vary for each image!
- Step 7: Lastly, when I tried the process above with different images, the problem was
that the picture which has a lot of dark areas always becomes nearly all black after
transformation, so I thought of a brightness technique such as gamma correction.

- - So basically I turned an image into a cartoon version ( like mangas ), but the thing is,
whenever I try to cartoonize a picture I must change the parameters,
##### def Cartoonifier(path, gamma=0.8, thresh=100)
So I thought why not use an auto-encoder and a data set of original+cartoonified images!
- Cartoonify a dataset of images manually and use diff parameters each time to get
the wanted effect!
- I trained an an encoder-decoder architecture where the encoder learns to extract features
from the realistic image, and the decoder generates the cartoonized version based on
these features. I used the previous dataset (with pairs of realistic and cartoon images for
training).

##### Future improvement?
- Use a bigger dataset of images.
- Fine-tune the model or adjust hyperparameters for better performance.
- Try it for Colorful images and not just grayscale.
