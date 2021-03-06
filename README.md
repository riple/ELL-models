
# The ELL Models Repository

This is a public repository of pretrained ELL models. 

## Model Naming

The ELL models repository contains a number of pretrained models suited for different device 
footprints. These models were generated by parameterizing a few neural network models that are 
known to work well, and generating a variety of related models based on these starting points. 
The model files themselves observe the following naming convention:

The filename will start with a short prefix identifying the general model architecture used to train the network. The 
prefixes are `v`, `d`, and `a`.

Following the prefix will the an underscore (`_`), followed by an encoding of the input dimension,
followed by encodings of the layers present in the model. This encoding uses a single upper-case
letter to represent a layerThe layer types and their encodings are:

| Layer         | Abbrev |
|--------------------|---|
| Input              | I |
| Convolution        | C |
| Binary convolution | B |
| Variable-bit conv  | V |
| Max pooling        | M |
| Average pooling    | A |
| Fully-connected    | F |
| Softmax            | S |

The parameters of the various layers will generally be determined by the architecture, but where
necessary, parameters may be added immediately following the layer abbreviation. 
For instance, a convolutional layer in the 'd' model type uses a 3x3 window for its convolutional 
layers, except for the last, which uses a 1x1 spatial window. The identifier for a full 'd' model 
would look like:

```
d_I224x224x3CMCMCMCMCMCMC1AS
```

Since many of the models we use alter the structure of the base model they're inspired by, we need to 
encode the parameters that vary as well. An example of a 'v' model with a single fully-connected layer, 
and of size 3072, would be:

```
v_I112x112x3BBMCCMCCCMCCCMCBBMF3072
```

## Code of Conduct

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

