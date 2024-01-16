# Transformer-Based-Synthetic-Battery-Data-Generation

## Get Started
This project has been executed via google colab.

### Steps to follow
1. Download the code as a zip file and extract the contents.

2. Create a new folder in google drive and upload the extracted contents into it.

3. The code to be executed in google colab: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/18jUpqb6Lfi4UFiECQf8-QPAuo4PWc6HL?usp=sharing)
4.  Make the necessary changes mentioned in the code to get the result.
 
5. The datsasets used can be found in the `datasets` folder. Any new dataset to be used should be uploaded in the mentioned folder.
 
6. All changes pertaining to prediction length, dataset etc can be done in `run_longExp.py` script and `Battery.sh` script. 

7. The dataset can be changed in `run_longExp.py`  and in `data_loader.py` (The name of the csv file used should be mentioned under the `data_path` parameter. The target parameter can be varied under the parameter `target`).
8. The number of epochs can be changed in the `run_longExp.py` file under the parameter 'train_epochs'


## Usage

To train and evaluate the PatchTST model on a dataset the following command is used in the google colab notebook :

```train & evaluate
!sh /content/drive/MyDrive/PatchTSTbat/PatchTST_supervised/Battery.sh
```
The detailed descriptions about the arguments are as following:

| Parameter name | Description of parameter |
| --- | --- |
| features | The forecasting task (defaults to `M`). This can be set to `M`,`S`,`MS` (M : multivariate predict multivariate, S : univariate predict univariate, MS : multivariate predict univariate) |
| seq_len | Sequence length refers to the number of data points or time steps in a sequence. |
| label_len | Label length refers to the length of the sequence used as the target or ground truth during the training or evaluation of the model |
| pred_len | Prediction length refers to the number of time steps into the future for which the model generates predictions. |
| target | Refers to the target variable chosen from the dataset |
| freq | Freq for time features encoding (defaults to `h`). This can be set to `s`,`t`,`h`,`d`,`b`,`w`,`m` (s:secondly, t:minutely, h:hourly, d:daily, b:business days, w:weekly, m:monthly |

On running the main code a `logs` folder is created in which the prediction output is stored. Another folder called `results` is also stored which has the predictions and the ground truth values from which plots can be obtained. The error values upon each execution of the shell script is stored in a `result.txt` file.

## Acknowledgments 
We appreciate the following github repository a lot for their valuable code base </br>
https://github.com/yuqinie98/PatchTST/tree/main/PatchTST_supervised

Dataset source : Diao, W., Saxena, S., Pecht, M. Accelerated Cycle Life Testing and Capacity Degradation Modeling of LiCoO2 -graphite Cells. J. Power Sources 2019, 435, 226830. </br>
https://web.calce.umd.edu/batteries/data.htm
