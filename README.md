# Parameter selection for contour saliency map transformations

This repository contains the code for the paper:

```
F.d.C.  Belém, J. Cousty, Z. K. do Patrocınio Jr, and S.J.F. Guimaraes. 
Impacts of contour saliency map transformations. In Graphics, Patterns and Images (SIBGRAPI),
2017 30th SIBGRAPI Conference on. IEEE, 2017.
 ```
```
@inproceedings{belem2017impacts,
  title={Impacts of contour saliency map transformations},
  author={Bel{\'e}m, Felipe de C and Cousty, Jean and do Patroc{\i}nio Jr, Zenilton KG and Guimaraes, Silvio Jamil F},
  year={2017},
  booktitle={Graphics, Patterns and Images (SIBGRAPI), 2017 30th SIBGRAPI Conference on},
  organization={IEEE}
}
```
## Work Overview 

In image processing, in order to visualize a segmentation result produced by saliency map approaches, a normalizing function is needed. Accordingly, studies have shown that by using a sigmoid function as a pre-filtering step and as a normalization one, can, in some ways, prevent over-segmentation. However, by applying this function, certain parameters need to be defined in order to achieve the best results. Therefore, this study will, with the assistance of machine learning, define parameters that could be more assertive than the previous selected proposition and generate better segmentation events.

The current study proposes the use of regression algorithms to obtain optimal sigmoidal parameters, in the pre-filtering step, of contour saliency map transformations proposed in Belém et. al, since its selection, during their study, was done empirically. The dataset used during this study was the BSDS500, consisting of 261.6 MB of information distributed between 500 '.ppm' extension images of various scenario situations.

In order to establish an approximation of the best configuration for each image, a semi-supervised approach was considered, such that the regression was made possible. Experimental results show that an optimal parameter can be estimated by a Random Forest model regarding texture-based features as input samples, overcoming other approaches (like SVR), and obtaining a better performance than the result presented by Belém et. al.

### Experimental Results
![results](results.png)

## Usage 

### IT IS NECESSARY TO HAVE SCIKIT-LEARN, SCIKIT-IMAGE AND NUMPY INSTALLED

In an Linux environment, simply run the command below in order to compile the program
```
./compile
```
If a cleanup is desired, the command below is sufficient
```
make clean
```
Then, if the compilation was successfull, you can perform one of the commands below in order to obtain the results from each approach
```
./runBelemEtAl.sh <path/to/image> <path/of/result>
./runWithLinReg.sh <path/to/image> <path/of/result>
./runWithGLCM.sh <path/to/image> <path/of/result>
./runWithSVR.sh <path/to/image> <path/of/result>
./runWithRF.sh <path/to/image> <path/of/result>
```
The segmentation algorithm is based on the previous work of Belém et al., which is an extension of the work of Cousty et al.

For more information, see the README files within each folder
