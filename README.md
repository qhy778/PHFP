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
### Average performance comparison
<left><img width="100%" alt="" src="assets/result4.png"/></left>

## Presentation Demo
[![[Demo] Progressive Hierarchical Feature Periodic Transformer for Robust UAV Tracking - YouTube](https://i.ytimg.com/vi/9x4YBBV-UwI/maxresdefault.jpg)](https://www.youtube.com/watch?v=9x4YBBV-UwI "[Demo] Progressive Hierarchical Feature Periodic Transformer for Robust UAV Tracking - YouTube")


## Usage
### Installation
Create and activate a conda environment:
```
conda create -n FP python=3.8
conda activate FP
```
Install the required packages:
```
pip install -r requirements.txt
```

### Data Preparation
Put the tracking datasets in ./data. It should look like this:
 


## Acknowledgment
This repo is based on [OSTrack](https://github.com/botaoye/OSTrack) and [PyTracking](https://github.com/visionml/pytracking) library which are excellent works and help us to quickly implement our ideas.


## Contact
If you have any question, feel free to email quhaoyu7077@163.com.
