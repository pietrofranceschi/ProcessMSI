# ProcessMSI
Data analysis workflow for targeted MSI imaging experiments

* Depends on

```
MALDIquant, msprocess
```
Example

```
filepath  = 'C:\\folder\\drug'           ## MSI data folder path

 filename ='drug'                        ## filename to save csv files<br/>
 
 mzs = c(284.2, 281.2, 289.2)      ## mass list for drug, tissue and internal standard (optional) ion peaks

```

## Details 
The preprocessing of targeted MSI data in our study is performed in following steps:

1. First, a reference mass bin of size 0.5 was created.

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/BinnedSpectrum.png)

2. Peak selection was performed based on local maxima search in desired bins which in our case three ion peaks, namely: drug (m/z = 284.01-284.23), tissue (m/z=281.16-281.44), and internal standard (m/z= 289.1-289.3) were selected. 

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/zoombinnedspectrum.png)

3.  In peak selection step, signal-to-noise value was estimated for each spectrum separately by sorting the intensity value in descending order and look in lower intensity region. 

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/PeakSelection.png)

4. Drug, tissue and internal standard ion images were created. And, drug and tissue ion images were normalized with internal standard ion image. 

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/IonImage.png)

5. Density-based thresholding was performed on tissue ion image to separate tumor tissue from the background area.

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/MaskImg.png)

6. Final drug image was further smoothen using median filtering.

![alt text](https://github.com/pietrofranceschi/ProcessMSI/blob/master/FinalionImages.png)




