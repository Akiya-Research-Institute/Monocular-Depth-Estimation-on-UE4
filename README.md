# Monocular Depth estimation on UE4 and UE5

Example UE project for depth estimation using a single RGB camera.  
See [ue5 branch](https://github.com/Akiya-Research-Institute/Monocular-Depth-Estimation-on-UE/tree/ue5) to use with UE5.  
[(日本語の説明はこちら)](https://akiya-research-institute.github.io/NNEngine-API/ja/demo-project-overview-depth-estimation/
)  

https://user-images.githubusercontent.com/89242761/154613825-dccfd6a0-5617-4e2a-aa8b-63f92d0131a4.mp4

(DPT model demo)

https://user-images.githubusercontent.com/89242761/154831579-bd692f95-278c-47b1-952f-fd360948473e.mp4

## Environment

- OS: Windows 10 64bit
- Unreal Engine: 4.26.2
- [NNEngine plugin](https://www.fab.com/listings/67591270-75f6-456d-aa89-c64e1e0ee05f)

## Download

Please download from the [release](https://github.com/Akiya-Research-Institute/Monocular-Depth-Estimation-on-UE4/releases) page.

## Run the demo

1. Extract the downloaded zip file and double-click `MonoDepthEstimation.uproject`.  
2. After launching, click `Play` on the editor to start the demo that performs AI estimation for the pre-recorded video.
3. To run on your webcam, specify the webcam you want to use in `/Content/Common/MediaPlayer_webcam.uasset`.

## Step-by-step guide to implementation

[![Step-by-step guideat youtube](http://img.youtube.com/vi/sTSlhYOePDE/0.jpg)](http://www.youtube.com/watch?v=sTSlhYOePDE)

## Additional models

### Large model

If you want to use the large model (whose input image size is 384x384), download from [here (GitHub Release page)](https://github.com/Akiya-Research-Institute/Monocular-Depth-Estimation-on-UE4/releases/download/v1.1/midas_1x384x384xBGRxByte.onnx) or [here (Google Drive)](https://drive.google.com/file/d/1ml45494AGppnSZ3ivhw-HPi9CE8hxY2J/view?usp=sharing) and place it under `Source\ThirdParty\Models`.

### DPT model

To use DPT model, download model from [here (GitHub Release page)](https://github.com/Akiya-Research-Institute/Monocular-Depth-Estimation-on-UE4/releases/download/v1.3/dpt_hybrid_256x320.onnx) or [here (Google Drive)](https://drive.google.com/file/d/12mLc0usb0qLb5LlKhE1EEQhP7Kyp1qiH/view?usp=sharing) and place it under `Source\ThirdParty\Models`. Then, open `/Content/DepthEstimation/DPT/test_DPT.map` and click `Play`.

### TCMonoDepth model

To use TCMonoDepth model, download model from [here (GitHub Release page)](https://github.com/Akiya-Research-Institute/Monocular-Depth-Estimation-on-UE4/releases/download/v1.4/TCMonoDepth_1x384x384xBGRxByte.onnx) or [here (Google Drive)](https://drive.google.com/file/d/1lbLcU2J_mHwI2C3_jdIeWpuiUS6M68a-/view?usp=sharing) and place it under `Source\ThirdParty\Models`. Then, open `/Content/DepthEstimation/TCMonoDepth/test_TCMonoDepth.map` and click `Play`.

## Display camera image to the preview mesh

By switching the base color pin of `/Content/DepthEstimation/Grayscale_WPO.uasset`, you can 
display camera image to the preview mesh.

## Model details

See the following pages for the details of the model used in this project.

### Default and large models

- [Towards Robust Monocular Depth Estimation: Mixing Datasets for Zero-shot Cross-dataset Transfer](https://arxiv.org/abs/1907.01341)
- [GitHub](https://github.com/isl-org/MiDaS)

### DPT model

- [Vision Transformers for Dense Prediction](https://arxiv.org/abs/2103.13413)
- [GitHub](https://github.com/isl-org/DPT)

Converted to ONNX by

- [PINTO_model_zoo](https://github.com/PINTO0309/PINTO_model_zoo)

### TCMonoDepth model

- [Enforcing Temporal Consistency in Video Depth Estimation](https://openaccess.thecvf.com/content/ICCV2021W/PBDL/papers/Li_Enforcing_Temporal_Consistency_in_Video_Depth_Estimation_ICCVW_2021_paper.pdf)
- [GitHub](https://github.com/yu-li/TCMonoDepth)
