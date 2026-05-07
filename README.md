# CA-LIC: Chroma-Aware Learned Image Compression for Machines
<p align="justify">
Image Compression for Machines (ICM) aims to remove visual redundancies while preserving downstream machine vision performance. Existing learned ICM methods primarily focused on task-relevant region preservation and task-driven rate-distortion optimization. However, luma and chroma components exhibit asymmetric functional importance in machine vision, and how to exploit this asymmetry for machine-oriented redundancy reduction has been largely overlooked. To address this issue, we propose a Chroma-Aware Learned Image Compression (CA-LIC) method that performs differentiated processing to luma and chroma components based on their respective perceptual roles in downstream machine vision tasks. Specifically, a Chroma Adaptive Sampling Coding (CASC) strategy is developed, in which a Superpixel-based Chroma Sampling Module (SCSM) reduces chroma data volume via adaptive region-level semantic aggregation, and a Chroma Generation Module (CGM) enhances reconstructed chroma fidelity through luma-guided compensation. Furthermore, a Cross-component Feature Transform Module (CFTM) is designed to bridge the spatial structure gap between luma and sampled chroma representations and reduce cross-component redundancies irrelevant to downstream task performance. Experimental results demonstrate that the proposed CA-LIC achieves superior compression efficiency, yielding a BD-rate saving of 48.53% and a BD-mAP gain of 8.12\% for object detection, and a BD-rate saving of 44.92% and a BD-mAP gain of 7.48% for instance segmentation on the COCO2017 dataset, compared with the anchor VVC-Intra (VTM 20.0), while also outperforming other state-of-the-art image compression methods.
</p>

<div align="center">
    <img src="https://github.com/qwerty20253/CA-LIC/blob/main/new_folder/framework.png" alt="framework" width="100%" />
</div>

## 1 Experimental Results
(1) The complete bpp and mAP@0.50/mIoU results of the anchor VVC-Intra (VTM 20.0)
<div align="center">
    <img src="https://github.com/qwerty20253/CA-LIC/blob/main/new_folder/VVC_Intra.png" alt="VVC_Intra" width="80%" />
</div>

(2) The complete bpp and mAP@0.50 results of each image compression method on the COCO2017 dataset
<div align="center">
    <img src="https://github.com/qwerty20253/CA-LIC/blob/main/new_folder/COCO2017.png" alt="COCO2017" width="100%" />
</div>

(3) The complete bpp and mAP@0.50 results of each image compression method on the OpenImagesV6 dataset
<div align="center">
    <img src="https://github.com/qwerty20253/CA-LIC/blob/main/new_folder/OpenImagesV6.png" alt="OpenImagesV6" width="100%" />
</div>

(4) The complete bpp and mAP@0.50 results of each image compression method on the VOC2012 dataset
<div align="center">
    <img src="https://github.com/qwerty20253/CA-LIC/blob/main/new_folder/VOC2012.png" alt="VOC2012" width="55%" />
</div>

## 2 Usage
(1) Training
python train_color_generate_fusion_task.py

(2) Evaluation
object detection: python mytest_dec.py

instance segmentation: python mytest_seg.py

(3) Pretrained Model
| Quality | Lambda | Link |
| :--- | :--- | :--- |
| 1 | 0.001 | [link](https://pan.baidu.com/disk/main?from=homeFlow#/index?category=all&path=%2Fcoding_file%2Fsave_model%2F1e-3/model_best.pth.tar) |
| 2 | 0.0025 | [link](https://pan.baidu.com/disk/main?from=homeFlow#/index?category=all&path=%2Fcoding_file%2Fsave_model%2F2.5e-3/model_best.pth.tar) |
| 3 | 0.005 | [link](https://pan.baidu.com/disk/main?from=homeFlow#/index?category=all&path=%2Fcoding_file%2Fsave_model%2F5e-3/model_best.pth.tar) |
| 4 | 0.01 | [link](https://pan.baidu.com/disk/main?from=homeFlow#/index?category=all&path=%2Fcoding_file%2Fsave_model%2F1e-2/model_best.pth.tar) |

## 3 Requirements
* torch==2.4.1  
* tensorboard==2.14.0  
* numpy==1.22.4  
* detectron2  
* compressAI  




