## Applying texture compression using VVC H.266

Texture Compression where Geometry constant:

# R1 (High Quality, Low Compression)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 25 --output output_file_R1.vvc
```

# R2
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 30 --output output_file_R2.vvc
```

# R3
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 35 --output output_file_R3.vvc
```

# R4
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 40 --output output_file_R4.vvc
```

# R5 (Low Quality, High Compression)
```bash
vvencapp.exe -i input_file.yuv --size 1024x1024 --fps 25 --format yuv420 --qp 55 --output output_file_R5.vvc
```
# Explanation:
- **R1**: QP = 25 (High Quality, Low Compression)
- **R2**: QP = 30
- **R3**: QP = 35
- **R4**: QP = 40
- **R5**: QP = 55 (Low Quality, High Compression)

Geometry QP is kept constant, while Texture QP is varied.
- **Input and Output paths** (`input_file.yuv` and `output_file_R1.vvc`, etc.) should be replaced with the actual paths relevant to your environment.

## Note
Please follow the file convert_yuv_to_vvc for downloading vvenc and process how to install and use it. Make sure to change the input and output file paths.
