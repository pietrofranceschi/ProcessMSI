# ProcessMSI
Data analysis workflow for targeted MSI imaging experiments

## Details 
The preprocessing of targeted MSI data in our study is performed in following steps:

1. First, a reference mass bin was created of size 0.5.
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/BinnedSpectrum.png)

2. Then, within desired mass bins, in our case, three ion peaks, namely: drug, tissue, and internal standard ion were selected. 
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/binnedspectrumzoom.png)

3. Peak selection was performed based on local maxima search in respective bins. In peak selection step, signal-to-noise value will estimate for each spectrum separately by sorting the intensity value in descending order and look in lower intensity region. 
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/snrspectrum.png)

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/ZoomedPickedspectrum.png)

4. Drug, tissue and internal standard ion images were created. And, drug and tissue ion images were normalized with internal standard ion image. 
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/IonImage.png)

5. Density-based thresholding was performed on tissue ion image to separate tumor tissue from the background area.
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/MaskImg.png)

6. Final drug image was further smoothen using median filtering.
![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/FinalionImages.png)




