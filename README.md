# Image-Processing
  Cancer-Detection-by-Image-Processing

## Abstract
Region growing segmentation have been widely used especially in the medical area. However, the problem with it is the selection of initial seed points would affect the accuracy of the segmentation results. In this project, I have implemented three seed selection algorithms and compared the segmentation results based on one lung CT scan image. All of them have achieve great segmentation results, even the seeds selected are different, and the process and required working time is very different, as describe in the conclusion.

## Metholody flow chart
![Metholody flow chart](https://github.com/cathyhuangli/Computer-Vision-and-Machine-Learning/blob/master/C%20STEP.png)

## Result
![Result](https://github.com/cathyhuangli/Computer-Vision-and-Machine-Learning/blob/master/Result.png)

The three seed-selection algorithm leads to similar results for segmentation on the image. And the segmentation results are good with very little overlap between different regions. However, the clustering based seed selection is automatically efficient, without extra efforts from human to assist in the seed selection. While high-level knowledge based algorithm require the most efforts from human to input the selected seeds, histogram thresh holding based algorithm require human to identify the center of region after thresh holding on the original image. 

The problem with high-level knowledge based algorithm is that it expects initial seeds selection is from an expert in Lung cancer CT image, however, this is not the case when I am processing it. I have a hard time to choose one image that definitely looks abnormal and I can identify which part is abnormal. That is why the image is chosen in this paper.

The problem with histogram based seed selection algorithm is that histogram thresh holding only differentiate intensity level values instead of region/object. That is why the thresh holding results may include more than one region/object, and we have to manually locate the center as there are multiple objects/region in the thresh holding results.

The problem with clustering based seed selection is to decide the k, as if k is too small, the segmentation would not be able to capture all the different objects in the image; and if k is too big, it would cost extra time for the segmentation process. In this case, I have initially tried k=5, it turns out missing one object in the segmentation results; and when I increase k to 6, the segmentation results captured all the objects/parts in the image, with one duplicated parts.

In future research, statistical evaluation of segmentation could be introduced into the comparison like percent lover lap, variability index. 
  
## Conclusion

I have implemented three algorithms to choose initial seeds in region growing segmentation, even though the initial seeds selected by clustering based algorithm are not necessarily in the center of the region as the other two algorithms, the segmentation results reached similar effect. The position of the initial seeds does affect the segmentation results, but since we have smoothed the image to reduce noises and the seeds are not outside of the region, the results are still satisfying.
 
  My research is mainly implementation based and the comparison of different algorithm is based on one image given the fact that high-level knowledge based seed selection require knowledge about lung cancer and require selecting the initial seeds one by one visually and manually. Possible future research direction could include: Increase high-level knowledge on lung CT scan image; Automatic the histogram thresh holding based seed selection; Test the algorithm on more images to formalize a quantitative comparison; Include color-image region segmentation technique for seed selection. 



References 
[1] Luis Garcia Ugarriza, Eli Saber, Sreenath Rao Vantaram, Vincent Amuso, Mark Shaw and Ranjit Bhaskar, "Automatic Image Segmentation by Dynamic Region Growth and Multiresolution Merging," IEEE Trans. Image Process., vol 18, No 10, pp 2275-2288, Oct 2009
[2] Jianping Fan, David. K.Y.Yau, Ahmed. K.Elmangarmid, and Walid G. Aref, " Automatic Image Segmentation by Integrating Color-Edge Extraction and Seeded Region Growing," IEEE Trans. Image Process., vol 10, No. 10, pp 1454- 1466, Oct 2001
[3] Keri Woods, "Genetic Algorithms : Colour Image Segmentation Literature Review", July 2007
[4] Frank Y. Shih and Shouxian Cheng, "Automatic seeded region growing for color image segmentation," Science direct, Image and vision computing 23(2005) 877-886
[5] N. Ikonomakis, K.N. Plataniotis, M. Zervakis, and A.N. Venetsanopoulos, "Region Growing And Region Merging Image Segmentation," Proceedings Of IEEE Conference On Digital Signal Processing 1(1997) pp 299-302
[6] A.Q. Al-Faris, N. Umi Kalthum, N.A.MatIsa, and I.L. Shuaib, Computer-Aided Segmentation System for Breast MRI Tumour using Modified Automatic Seeded Region Growing, (BMRI-MASRG)”, J Digit Imaging Vol 27, pp 133–144, 2014.
[7] shan J,Cheng HD, WangY. novel automatic seed point selection algorithm for breast ultrasound images. 19th international conference on pattern recognition. 2008:1-4
[8] M. Mary Synthuja Jain Preetha, L.Padma Suresh, MJohn Bosco,," Image Segmentation Using Seeded Region Growing,.", 2012 International Conference on Computing, Electronics and Electrical Technologies
