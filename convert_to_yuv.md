# Converting PNG Images to YUV Videos using FFmpeg

This document outlines the steps and FFmpeg commands used to convert a sequence of PNG images into YUV videos.

## Prerequisites

Installing FFmpeg on Windows.

## Download FFmpeg:

Visit the official FFmpeg website: 
```bash
https://ffmpeg.org/download.html 
```
Click on "Windows" under "Get packages & executable files."
Choose a Windows build (e.g., "gyan.dev" builds).
Download the latest release of the "Full" version.
Extract the Downloaded Zip File:

Once downloaded, extract the ZIP file to a location of your choice (e.g., C:\ffmpeg).

## Add FFmpeg to System Path:

Open the Start Menu, search for "Environment Variables," and select "Edit the system environment variables."
In the "System Properties" window, click "Environment Variables."
Under "System variables," find and select the "Path" variable, then click "Edit."
Click "New" and add the path to the bin directory inside the extracted FFmpeg folder (e.g., C:\ffmpeg\bin).
Click "OK" on all windows to apply the changes.
Verify Installation:

## Open a Command Prompt and type ffmpeg -version.

## Step 1: Create the txt file containing images path. (use the file: generate_images_path_list.ipynb)

## Step 2: Opening Command Prompt as Administrator

Press Win + S on your keyboard to open the search bar.
Type cmd or Command Prompt.
Right-click on Command Prompt from the search results.
Select "Run as administrator" from the context menu.
A User Account Control (UAC) window may appear, asking for permission to make changes. Click Yes.

## Commands to Convert PNG to YUV

```bash
ffmpeg -f concat -safe 0 -r 25 -i input_file_list.txt -pix_fmt yuv420p -c
rawvideo output_file.yuv
```

Explanation of each part:

 ffmpeg: The command-line tool for processing video and audio files.
-f concat: Specifies the input format, in this case, "concat," which tells FFmpeg to concatenate multiple input files.
-safe 0: This option is used to disable security restrictions, allowing you to use absolute paths in the input file list.
-r 25: Sets the frame rate of the output video to 25 frames per second.
-i input_file_list.txt: Specifies the input file, which contains a list of file paths to be concatenated.
-pix_fmt yuv420p: Sets the pixel format of the output video to yuv420p, which is widely supported and commonly used for compatibility.
-c:v rawvideo: Specifies the video codec to be used. In this case, raw video means that the output will be uncompressed raw video data.
output_file.yuv: The name of the output file where the processed video will be saved.

## Sample commands:

Soldier:
```bash
ffmpeg -f concat -safe 0 -r 25 -i F:/8iVFBv2/8iVFBv2/soldier/Png_with_grey_background_list_ffmpeg.txt -pix_fmt yuv420p -c:v rawvideo F:/8iVFBv2/8iVFBv2/soldier/soldier_grey_vox10_01.yuv
```

Loot:
```bash
ffmpeg -f concat -safe 0 -r 25 -i F:/8iVFBv2/8iVFBv2/loot/Png_with_grey_background_list_ffmpeg.txt -pix_fmt yuv420p -c:v rawvideo F:/8iVFBv2/8iVFBv2/loot/loot_grey_vox10_01.yuv
 ```

Long dress:
```bash
ffmpeg -f concat -safe 0 -r 25 -i F:/8iVFBv2/8iVFBv2/longdress/Png_with_grey_background_list_ffmpeg.txt -pix_fmt yuv420p -c:v rawvideo F:/8iVFBv2/8iVFBv2/longdress/longdress_grey90_vox10_01.yuv
```

RedandBlack:
```bash
ffmpeg -f concat -safe 0 -r 25 -i F:/8iVFBv2/8iVFBv2/resandblack/Png_with_grey_background_list_ffmpeg.txt -pix_fmt yuv420p -c:v rawvideo F:/8iVFBv2/8iVFBv2/resandblack/resandblack_grey90_vox10_01.yuv
 ```


## Note: 
Make sure to change the file paths according to you, while using the command.


