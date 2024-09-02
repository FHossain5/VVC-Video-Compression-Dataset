# Compressing YUV Videos to VVC Format using VVenC

This document outlines the steps and commands used to compress YUV videos into VVC (H.266) format using the VVenC encoder.

## Prerequisites

Installing VVenC on Windows.

## Download VVenC:

Visit the official VVenC GitHub repository
```bash
https://github.com/fraunhoferhhi/vvenc
```
Scroll down to the "Releases" section.
Download the latest release version suitable for your operating system.
Extract the downloaded ZIP file to a location of your choice (e.g., C:\vvenc).

## Add VVenC to System Path:

Open the Start Menu, search "Environment Variables," and select "Edit the system environment variables."
In the "System Properties" window, click "Environment Variables."
Under "System variables," find and select the "Path" variable, then click "Edit."
Click "New" and add the path to the bin directory inside the extracted VVenC folder (e.g., C:\vvenc\bin).
Click "OK" on all windows to apply the changes.

# Verify Installation:
Open a Command Prompt and type:
```bash
vvencapp.exe --help
```

# Step 1: Prepare YUV Video Files
follow the convert_to_yuv.md file

# Step 2: Opening Command Prompt as Administrator

Press Win + S on your keyboard to open the search bar.
Type cmd or Command Prompt.
Right-click on Command Prompt from the search results.
Select "Run as administrator" from the context menu.
A User Account Control (UAC) window may appear, asking for permission to make changes. Click Yes.
Change the directory to where vvenc located. 

```bash
C:\vvence\bin\release-static\vvencapp.exe
```

# Command to Convert YUV to VVC (H.266)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 55 --output output_file.vvc
```
# Explanation of each part:

vvencapp.exe: The VVenC command-line tool for encoding YUV video to VVC format.
i input_file.yuv: Specifies the input YUV file.
size 1024x1024: Specifies the resolution of the input video. Replace 1024x1024 with your video's actual resolution.
fps 25: Sets the frame rate of the input video to 25 frames per second.
format yuv420: Specifies the pixel format of the input video. Ensure this matches your YUV video format.
qp 55: Sets the quantization parameter for compression. Lower values give higher quality, but larger file sizes.
output output_file.vvc: The name of the output file where the compressed video will be saved.


# Sample Commands:

**Soldier**
```bash
vvencapp.exe -i C:/Users/Hafsa/Downloads/Png/yuv_soldier/soldier_output.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 15 --output F:/Dataset/soldier/soldier_compression_videos/R5/R5_soldier_gc_black_vox10.vvc

```

**Loot**
```bash
vvencapp.exe -i C:/Users/Hafsa/Downloads/Png/yuv_loot/11_loot_greyoutput.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 15 --output F:/Dataset/loot/loot_75_compression_videos/texture_compression/R5/R5_loot_gc_black_vox10.vvc
```

Longdress
```bash
vvencapp.exe -i C:/Users/Hafsa/Downloads/Png/yuv_longdress/longdress_output.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 15 --output F:/Dataset/longdress/longdress_compression_videos/R5/R5_longdress_gc_black_vox10.vvc
```

RedandBlack
```bash
vvencapp.exe -i C:/Users/Hafsa/Downloads/Png/yuv_resandblack/resandblack_output.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 15 --output F:/Dataset/resandblack/resandblack_compression_videos/R5/R5_resandblack_gc_black_vox10.vvc
```

# Note
Make sure to change the file paths according to your setup when using the command. Adjust the resolution (--size), frame rate (--fps), and pixel format (--format) as needed for your specific YUV files.

