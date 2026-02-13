# [AAAI2025] Noisy Localization Annotation Refinement for Object Detection
<img width="1016" height="290" alt="image" src="https://github.com/user-attachments/assets/0b77b859-d6c6-487f-b0fc-6ecbb84cf5b0" />

## Model Zoo
<img width="578" height="665" alt="image" src="https://github.com/user-attachments/assets/af8e142f-62ef-487b-985e-cadc5ad85d9d" />

We've pre-trained  from scratch and evaluate on the `MSCOCO2017 val`. 

### Inference on MSCOCO2017 dataset
<img width="326" height="165" alt="image" src="https://github.com/user-attachments/assets/ab31fd4c-70e9-4007-bfd8-419a9a8b1569" />


<img width="928" height="385" alt="image" src="https://github.com/user-attachments/assets/2890c503-ae1c-407d-9fd7-18da41463ef9" />
<img width="214" height="243" alt="image" src="https://github.com/user-attachments/assets/ce794488-a9d5-4ee2-9538-16f0a1a6e2bf" />





## Getting started

### 1. Installation

Noisy Annotation Refinement for
Object Detection is developed based on `torch==2.3.0` `pytorch-cuda==12.1` and `CUDA Version==12.6`. 


#### 3.Create and activate a conda environment.
```bash
conda create -n mambayolo -y python=3.11
conda activate mambayolo
```

#### 4. Install torch

```bash
pip3 install torch===2.3.0 torchvision torchaudio
```

#### 5. Install Dependencies
```bash
pip install seaborn thop timm einops
cd selective_scan && pip install . && cd ..
pip install -v -e .
```

#### 6. Prepare MSCOCO2017 Dataset
Make sure your dataset structure as follows:
```
├── coco
│   ├── annotations
│   │   ├── instances_train2017.json
│   │   └── instances_val2017.json
│   ├── images
│   │   ├── train2017
│   │   └── val2017
│   ├── labels
│   │   ├── train2017
│   │   ├── val2017
```

#### 7. Training NLG-T
```bash
python mbyolo_train.py --task train --data ultralytics/cfg/datasets/coco.yaml \
 --config ultralytics/cfg/models/NLG/NLG-T.yaml \
--amp  --project ./output_dir/mscoco --name mambayolo_n
```

## Acknowledgement

This repo is modified from open source real-time object detection codebase [Ultralytics](https://github.com/ultralytics/ultralytics). The selective-scan from [VMamba](https://github.com/MzeroMiko/VMamba).

## Citations
If you find [NLG](https://github.com/HZAI-ZJNU/NLG) is useful in your research or applications, please consider giving us a star 🌟 and citing it.

```bibtex
@misc{wang2024mambayolossmsbasedyolo,
      title={Mamba YOLO: SSMs-Based YOLO For Object Detection}, 
      author={Zeyu Wang and Chen Li and Huiying Xu and Xinzhong Zhu},
      year={2024},
      eprint={2406.05835},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2406.05835}, 
}
```
