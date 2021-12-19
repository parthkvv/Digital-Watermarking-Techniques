# Introduction
Digital watermarking is technique of embedding data into digital forms such as image, video & audio data which helps in identifying the ownership of the data. This technique is useful for copyright protection, tamper resistance, theft-intimidation etc. and it should be fixed in such a way that naked eye cannot differentiate it, as growth of technologies in the digital side is becoming wider and wider chances of clone copies keep on increasing. We have tried to implement an algorithm for black and white (binary) digital image watermarking technique based on discrete wavelet transform, singular value decomposition and DCST to better protect the security of watermarked image.

# Working
# - Embedding : 
1. Host image is converted into a double type data and DCST compression is applied. 
2. The Discreet Wavelet Transformation(DWT) (2 Dimensional) is carried out twice onto the compressed host image rendering LL2 , HL2, LH2 and HH2 sub bands. 
3. The LL2 sub band is chosen for the proceeding operations that are to be performed on the image obtained in Step2. 
4. The image obtained in step 3 is resized to fit in for the application of SVD onto it. The SVD is then applied onto it. 
5. The watermark image is read and resized (the same procedure that was done on the host image in previous step). 
6. Mat2gray function is applied onto the watermark image to set all the values of the image matrix in the range of 0 to 1(grey scale image obtained). 
7. Watermark image converted to double type, SVD is performed onto it for the final embedding process. 
8. Watermark is embedded onto the host image, and sub bands are rebuilt (using SVD).

Additive White Gaussian noise is applied onto the watermarked image to test for robustness.

# - Extraction: 
1. Possibly corrupt watermarked image is read for analysis. 
2. DCST decomposition is applied.
3. DCST coefficients are subdivided(same as in embedding procedure). 
4. Singular values obtained from the image using SVD. 
5. Watermark is extracted using the unique alpha blending technique. 
6. Finally , inverse DCST and DWT are applied to procure the watermark from the pre-processed image.
Obtained watermarks and noisy images obtained from DOST and DCST based methods are then compared.
