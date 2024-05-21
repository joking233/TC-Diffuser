# TC-Diffuser
This project includes the code of our deep learning TC forecasting method TC-Diffuser.

## Requirements 
* python 3.8.8
* Pytorch 1.11.0 (GPU)

## Data Preparation
First, we need to download all the data we used in TropiCycloneNet.
* $TCN_{D}$'s [subset](https://drive.google.com/file/d/1YJg_gjF-zqvRdNpmAWFG4bG0Akwv_r2p/view?usp=sharing)
* Himawari-8 satellite [cloud image](https://drive.google.com/file/d/1xg6xxYxO_ASkI54C8tPyhNS1ceyrfv5b/view?usp=sharing)
* TC-Diffuser's [checkpoint](https://drive.google.com/file/d/1j5r2L5Y5W81pn7nBfrZCT1BA1_qfnaay/view?usp=sharing)

After completing the downloading, there are some files.
As for $TCN_{D}$'s subset, it includes BST data ($Data_{1d}$), ERA5 data($Data_{2d}$), and Environment data($Env-data$). You can extract them somewhere you like.

As for the Himawari-8 satellite cloud image, it will be used as the background of our track prediction results.

As for $TCN_{M}$'s checkpoint, it is our well-trained model, you need to move it to **\scripts\model_save\best** before you run our code.

## Test
```python
## Visualize some samples##
cd scripts
python visual_evaluate_model_Me.py --TC_name MALIKSI --TC_date 2018061006  --TC_img_path [Himawari-8 satellite cloud image path] --TC_data_path [$TCN_{D}$'s subset path]
```
**TC_name** and **TC_date** are the parameters presenting the TC you want to predict. You can change it and see some other predictions. Please check the TC in the folder **Himawari_airmass** and choose the TC to predict (at this moment, we just provided cloud images in the year 2018 and 2019).

After running the code (about 1 min), you can check the results at **\scripts\plot**
