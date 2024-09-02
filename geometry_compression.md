## Applying Geometry Compression using VVC H.266

Apply the compression on png or ply files using the compression.ipyub and then use this to make yuv videos using ffmpeg. (use convert_to_yuv.md)

### Geometry Compression where Texture is constant at QP 22:

### R1 (High Quality, Low Compression)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 50 --output output_file_R1.vvc
```

### R2
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 52 --output output_file_R2.vvc
```

### R3
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 53 --output output_file_R3.vvc
```

### R4
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 54 --output output_file_R4.vvc
```

### R5 (Low Quality, High Compression)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 55 --output output_file_R5.vvc
```

### Explanation:
- **R1**: Geometry QP = 50 (High Quality, Low Compression)
- **R2**: Geometry QP = 52
- **R3**: Geometry QP = 53
- **R4**: Geometry QP = 54
- **R5**: Geometry QP = 55 (Low Quality, High Compression)

In this case, **Texture QP is kept constant at 22**, while **Geometry QP is varied**.

- **Input and Output paths** (`input_file.yuv` and `output_file_R1.vvc`, etc.) should be replaced with the actual paths relevant to your environment.

---

### Note:
- Make sure to follow the instructions in the `convert_yuv_to_vvc.md` file for downloading and installing `vvenc` and understanding the process.
- Replace the input and output file paths with the correct ones for your environment.
