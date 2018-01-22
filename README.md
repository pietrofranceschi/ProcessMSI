# ProcessMSI
Data analysis workflow for targeted MSI imaging experiments


## Details 
The preprocessing of targeted MSI data is performed in following steps:

1. Create mass bin of size 0.5.
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/BinnedSpectrum.png)

2. Extract drug, tissue and internal standard (optional value) peaks for individual spectrum within their respective bins based on local maxima search. If m/z for tissue ion image is missing, then the drug m/z value will use to extract tissue ion image. 

3. In peak picking step, signal-to noise value will estimate for each spectrum separately by sorting the intensity value in descending order and look in lower intensity region. 

4. Create tumor masked image based on tissue ion image using density-based thresholding method.

5. Remove spatial noise using median filtering.
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/FinalionImages.png)
