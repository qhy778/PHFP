# PHFP

[Models & Raw Results](https://drive.google.com/drive/folders/11XOu-ZKYNaJfPoK1e7hb1Npy5UoV38Fl?usp=sharing)
Google Driver
| [Training Dataset Labels](https://drive.google.com/drive/folders/1EhOZqdjaLjrFNW8bHgTizj2-BX9ysrBP?usp=sharing)
Google Driver

<p align="center">
  <img width="85%" src="assets/result1.png" alt="Framework"/>
</p>


## Results
### UAV20L, UAVTrack112, UAVTrack112_L
<left><img width="100%" alt="" src="assets/result2.png"/></left>
### DTB70
<left><img width="100%" alt="" src="assets/result3.png"/></left>
<left><img width="100%" alt="" src="assets/result4.png"/></left>

## Presentation Demo

## Usage
### Installation
Create and activate a conda environment:
```
conda create -n FP python=3.9
conda activate FP
```
Install the required packages:
```
pip install -r requirements.txt
```

### Data Preparation
Put the tracking datasets in ./data. It should look like this:
 

### Path Setting
Run the following command to set paths:
```
cd <PATH_of_DCPT>
python tracking/create_default_local_file.py --workspace_dir . --data_dir ./data --save_dir ./output
```
You can also modify paths by these two files:
```
./lib/train/admin/local.py  # paths for training
./lib/test/evaluation/local.py  # paths for testing
```

### Training
Dowmload the pretrained [foundation model](https://drive.google.com/drive/folders/11XOu-ZKYNaJfPoK1e7hb1Npy5UoV38Fl?usp=sharing) (OSTrack with Corner Head) and put it under ./pretrained_models/.
```
python tracking/train.py --script DCPT --config DCPT_Gate --save_dir ./output --mode multiple --nproc_per_node 4 --use_wandb 0
```


### Testing
Download the model weights from [Google Drive](https://drive.google.com/drive/folders/11XOu-ZKYNaJfPoK1e7hb1Npy5UoV38Fl?usp=sharing) or [BaiduNetDisk](https://pan.baidu.com/s/1fWDA6ccLcoxSEQK9X2A5Jg?pwd=0dof)

Put the downloaded weights on `<PATH_of_DCPT>/output/checkpoints/train/DCPT/DCPT_Gate`

Change the corresponding values of `lib/test/evaluation/local.py` to the actual benchmark saving paths

Some testing examples:
- UAVDark135 or other off-line evaluated benchmarks (modify `--dataset` correspondingly)
```
python tracking/test.py DCPT DCPT_Gate --dataset uavdark135 --threads 16 --num_gpus 4
python tracking/analysis_results.py # need to modify tracker configs and names
```
- DarkTrack2021
```
python tracking/test.py DCPT DCPT_Gate --dataset darktrack2021 --threads 16 --num_gpus 4
python tracking/analysis_results.py # need to modify tracker configs and names
```
- NAT2021
```
python tracking/test.py DCPT DCPT_Gate --dataset nat2021 --threads 16 --num_gpus 4
python tracking/analysis_results.py # need to modify tracker configs and names
```
- NAT2021L
```
python tracking/test.py DCPT DCPT_Gate --dataset nat2021L --threads 16 --num_gpus 4
python tracking/analysis_results.py # need to modify tracker configs and names
```

### Test FLOPs, and Speed
```
# Profiling DCPT_Gate
python tracking/profile_model.py --script DCPT --config DCPT_Gate
```


## Acknowledgment
This repo is based on [OSTrack](https://github.com/botaoye/OSTrack) and [PyTracking](https://github.com/visionml/pytracking) library which are excellent works and help us to quickly implement our ideas.


## Contact
If you have any question, feel free to email quhaoyu7077@163.com.
