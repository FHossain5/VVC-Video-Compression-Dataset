## Applying Geometry & Texture Compression using VVC H.266

Apply the compression on png or ply files using the compression.ipyub and then use this to make yuv videos using ffmpeg. (use convert_to_yuv.md)

### Combined Geometry and Texture Compression:

### R1 (High Quality, Low Compression)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 57 --output output_file_R1.vvc
```
- **Geometry QP**: 57
- **Texture QP**: 15

### R2
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 59 --output output_file_R2.vvc
```
- **Geometry QP**: 59
- **Texture QP**: 20

### R3
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 60 --output output_file_R3.vvc
```
- **Geometry QP**: 60
- **Texture QP**: 25

### R4
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 61 --output output_file_R4.vvc
```
- **Geometry QP**: 61
- **Texture QP**: 30

### R5 (Low Quality, High Compression)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 62 --output output_file_R5.vvc
```
- **Geometry QP**: 62
- **Texture QP**: 35

### Explanation:
- **R1**: Geometry QP = 57, Texture QP = 15 (High Quality, Low Compression)
- **R2**: Geometry QP = 59, Texture QP = 20
- **R3**: Geometry QP = 60, Texture QP = 25
- **R4**: Geometry QP = 61, Texture QP = 30
- **R5**: Geometry QP = 62, Texture QP = 35 (Low Quality, High Compression)

In this case, **both Geometry and Texture QP values are varied**.

- **Input and Output paths** (`input_file.yuv` and `output_file_R1.vvc`, etc.) should be replaced with the actual paths relevant to your environment.

---

### Note:
- Ensure that you follow the instructions in the `convert_yuv_to_vvc.md` file for downloading and installing `vvenc` and understanding the process.
- Modify the input and output file paths to match your environment.

