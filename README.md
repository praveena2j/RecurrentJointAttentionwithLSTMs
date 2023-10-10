# Recursive Joint Attention of Audio-Visual Fusion for Dimensional Emotion Recognition
Code for our paper "Recursive Joint Attention for Audio-Visual Fusion in Regression Based Emotion Recognition" accepted to ICASSP 2023. Our paper can be found here https://ieeexplore.ieee.org/abstract/document/10095234.

## Citation

If you find this code useful for your research, please cite our paper.

```
@INPROCEEDINGS{10095234,
  author={Praveen, R Gnana and Granger, Eric and Cardinal, Patrick},
  booktitle={IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP)}, 
  title={Recursive Joint Attention for Audio-Visual Fusion in Regression Based Emotion Recognition}, 
  year={2023},
}
```

This code uses the Affwild2 dataset to validate the proposed approach for Dimensional Emotion Recognition. There are three major blocks in this repository to reproduce the results of our paper. This code uses Mixed Precision Training (torch.cuda.amp). The dependencies and packages required to reproduce the environment of this repository can be found in the `environment.yml` file. 

### Creating the environment
Create an environment using the `environment.yml` file

`conda env create -f environment.yml`

### Models
The pre-trained models of audio and visual backbones are obtained [here](https://github.com/kuhnkeF/ABAW2020TNT)
.The fusion models trained using our fusion approach can be found [here](https://drive.google.com/drive/folders/1W3c6V5bfGZTfwJLJq6ORSXXCLAsG7l2U?usp=share_link)

```
RJCA.model:  Fusion model trained using our approach on Affwild2 dataset
```

# Table of contents <a name="Table_of_Content"></a>

+ [Data Preprocessing](#DP) 
    + [Step One: Download the dataset](#PD)
    + [Step Two: Preprocess the visual modality](#PV) 
    + [Step Three: Preprocess the audio modality](#PA)
    + [Step Three: Preprocess the annotations](#PL)
+ [Training](#Training) 
    + [Step One: Training the backbones for individual modalities](#TD) 
    + [Step Two: Training the fusion model](#TE) 
+ [Inference](#R)
    + [Step One: Generating the results](#GR)
 
## Data Preprocessing <a name="DP"></a>
[Return to Table of Content](#Table_of_Content)

### Step One: Download the dataset <a name="PD"></a>
[Return to Table of Content](#Table_of_Content)

Please download the following.
+ [AffWild2 database (Valence-arousal Track)](https://ibug.doc.ic.ac.uk/resources/aff-wild2/), 
    + The cropped-aligned images are necessary. They are used to form the visual input. Otherwise, you may
    choose to use [OpenFace toolkit](https://github.com/TadasBaltrusaitis/OpenFace/releases) to extract the cropped-aligned images. But the per-frame success rate
    is lower compared to the database-provided version.

