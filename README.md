# VVC-Video-Compression-dataset

## Introduction
This dataset contains 350 video sequences created from the 8i Voxelized Full Bodies (8iVFB v2) dataset, utilizing the VVC (H.266) compression standard. The dataset is organized for experiments to compare the visual quality and compression efficiency of volumetric video sequences with modified geometry and texture parameters.

The dataset was created by converting PNG images to YUV format and then compressing the YUV videos using the VVC H.266 compression algorithm. These videos are categorized based on different compression levels for geometry and texture, and background variations (black and grey).

## Folder Structure
Below is a visual representation of the folder structure for the dataset to help you navigate through the video sequences:

```
-Videos_Dataset/
-│
-├── 50_videos_different_background/
-├── loot/
-├── soldier/
-├── readandblack/
-└── longdress/
```

### Folder Explanation:
**[loot/soldier/readandblack/longdress] Folders**:
These folders represent different subjects or sequences within the dataset. Each contains subfolders for the type of compression applied:

-**H266/**: Contains 88 files, each representing a video sequence compressed using the VVC (H.266) standard.
-**MP4/**: Contains 88 files, each representing the same video sequences compressed in MP4 format.

Each video sequence in these folders has a duration of 20 seconds.

## Video Creation Process
1. **Conversion to YUV**:  
   PNG images from the 8i Voxelized Full Bodies (8iVFB v2) dataset were converted to YUV format using FFmpeg. The YUV format is a raw video format suitable for compression using the VVC (H.266) codec.

2. **Compression using VVC (H.266)**:  
   The YUV files were then compressed using the VVC (H.266) codec, experimenting with different levels of quantization for both geometry and texture.

## Geometry Compression (Texture Constant)
- **R1 (High Quality, Low Compression)**: Geometry QP: 50, Texture QP: 22 (constant)
- **R2**: Geometry QP: 52, Texture QP: 22
- **R3**: Geometry QP: 53, Texture QP: 22
- **R4**: Geometry QP: 54, Texture QP: 22
- **R5 (Low Quality, High Compression)**: Geometry QP: 55, Texture QP: 22

## Texture Compression (Geometry Constant)
- **R1 (High Quality, Low Compression)**: Geometry QP: 28 (constant), Texture QP: 25
- **R2**: Geometry QP: 28, Texture QP: 30
- **R3**: Geometry QP: 28, Texture QP: 35
- **R4**: Geometry QP: 28, Texture QP: 40
- **R5 (Low Quality, High Compression)**: Geometry QP: 28, Texture QP: 55

## Geometry & Texture Compression
- **R1 (High Quality, Low Compression)**: Geometry QP: 57, Texture QP: 15
- **R2**: Geometry QP: 59, Texture QP: 20
- **R3**: Geometry QP: 60, Texture QP: 25
- **R4**: Geometry QP: 61, Texture QP: 30
- **R5 (Low Quality, High Compression)**: Geometry QP: 62, Texture QP: 35

## VVC Video Compression Dataset

- **VVC Video Dataset:** [Download](https://eu-north-1.console.aws.amazon.com/s3/buckets/vvdatasetcompress?region=eu-north-1&bucketType=general&prefix=videos_dataset/&showversions=false)
- **MP4 Video Dataset:** [Download](https://eu-north-1.console.aws.amazon.com/s3/buckets/vvdatasetcompress?region=eu-north-1&bucketType=general&prefix=VV_mp4_videos_dataset/&showversions=false)

# Volumetric-Video-dataset-dynamic-background

## Introduction
Volumetric video is an emerging technology that captures and represents real-world objects or scenes in 3D, allowing for an immersive viewing experience from multiple angles. This paper presents a comprehensive guide on creating volumetric videos using Blender, a free and open-source 3D creation suite. The guide details the process, which involves gathering the necessary 3D data in .PLY format, setting up the Blender environment, and utilizing various tools within Blender to convert the data into a volumetric representation. The aim is to assist creators in producing high-quality volumetric videos by providing step-by-step instructions, from the initial setup to the final rendering.

In addition, this dataset introduces a collection consisting of 175 video sequences, created from the 8i Voxelized Full Bodies (8iVFB v2) dataset. I specifically designed these sequences to incorporate a variety of background settings, including black, grey, and dynamic ones, providing a wide range of testing scenarios. This dataset serves as a valuable resource for experiments aimed at comparing the visual quality and compression efficiency of volumetric video sequences under different conditions.

## Folder Structure
Below is a visual representation of the folder structure for the dataset to help you navigate through the video sequences:

```
-Videos_Dataset/
-│
-├── 50_videos_different_background/
-│
-├── loot/
-│   ├── H266/
-│   └── MP4/
-│
-├── soldier/
-│   ├── H266/
-│   └── MP4/
-│
-├── readandblack/
-│   ├── H266/
-│   └── MP4/
-│
-└── longdress/
    ├── H266/
    └── MP4/
```
# Video Creation Guide

This repository provides a step-by-step guide for creating 360 degree videos using Blender, an open-source 3D creation suite.

## Quick Overview

1. **Set Up Blender**: Prepare Blender for volumetric video creation.
2. **Import 3D Model**: Bring your .PLY files into Blender.
3. **Create Materials**: Apply materials to your model for texturing.
4. **Use Geometry Nodes**: Convert the model into a volumetric representation.
5. **Render the Video**: Set up the scene and render your video.

For detailed instructions, see [Video Creation Process](create_volumetric_video.md).

# Video Creation Process

Follow these steps to create your own volumetric video using Blender.

## 1. Set Up Blender

- Open Blender.
- In the Properties panel on the right, click on the Render Properties tab (camera icon).
- Set the **Render Engine** to **Cycles** for high-quality results.

## 2. Import 3D Model

- Go to **File > Import > Stanford (.ply)**.
- Navigate to your .PLY file, select it, and click **Import**.
- If the model is not visible in the viewport, adjust the view or the model’s position.

## 3. Create Materials

- Switch to the **Shading** workspace.
- In the Shader Editor, click **New** to create a new material.
- Press **Shift + A** to add an **Attribute** node.
- In the Attribute node, type 'Col' (short for Color).
- Connect the Color output of the Attribute node to the Base Color input of the Principled BSDF shader.

## 4. Use Geometry Nodes

- Switch to the **Geometry Nodes** workspace.
- Click **New** to start a new node tree.
- Press **Shift + A** and navigate to **Geometry > Mesh to Points**.
- Place the Mesh to Points node between the Group Input and Group Output nodes in the node editor.
- You should now see your model as a point cloud in the viewport.

## 5. Render the Video

- Set up cameras, lights, and any other scene elements.
- Go to the Render Properties tab and adjust settings such as Samples and Output Resolution to balance quality and render time.
- Go to **Render > Render Animation** to start rendering your video.

Blender will render each frame of animation, which we can compile into a video file.

---

Congratulations! we created a 360 degree video using Blender.

## Volumetic Video Dataset(dynamic background)

- **LONG DRESS:** [Download](https://eu-north-1.console.aws.amazon.com/s3/buckets/volumeticvideodataset?region=eu-north-1&bucketType=general&prefix=LONG+DRESS/&showversions=false)
- **LOOT:** [Download](https://eu-north-1.console.aws.amazon.com/s3/buckets/volumeticvideodataset?region=eu-north-1&bucketType=general&prefix=LOOT/&showversions=false)
- **SOLDIER:** [Download](https://eu-north-1.console.aws.amazon.com/s3/buckets/volumeticvideodataset?region=eu-north-1&bucketType=general&prefix=SOLDIER-1/&showversions=false)
- **RESANDBLACK:** [Download](https://eu-north-1.console.aws.amazon.com/s3/buckets/volumeticvideodataset?region=eu-north-1&bucketType=general&prefix=RED+AND+BLACK/&showversions=false)


## Conclusion
This dataset serves as a valuable resource for exploring the efficiency and performance of the VVC (H.266) codec for volumetric video sequences. By providing different compression levels for geometry and texture, as well as videos with varying backgrounds, the dataset offers a comprehensive framework for comparing compression quality, visual artifacts, and performance.


