# Nvidia GPU Architecture Evolution

## Nvidia Hardware Terminology

See in this page: [Nvidia Hardware Terminology](nvidia_hardware_term.md)

## Timeline

- 2016 -- Pascal
- 2017 -- Volta
- 2018 -- Turing
- 2020 -- Ampere
- 2022 -- Hopper
- 2024 -- Blackwell
- 2025+ -- Rubin

### Pascal

Introduce HBM2, NVLink1.0(160GB/s), Unified memory architecture

Representitive products:

- GTX 1060, 1070 and 1080ti
- Tesla P100
- Quadro P6000

Those cards doesn't have Tensor Cores. Therefore, they performed poorly during AI training.

### Volta

Introduce Tensor Cores 1.0, NVLink 2.0(300GB/s)

Representitive products:

- Tesla V100
    - 16G/32G HBM2
    - FP16 performance: 125 TFLOPS

### Turing

Introduce Tensor Cores 2.0(Append INT8, INT4), RT Cores, DLSS

Representitive Products:

- RTX 2060, 2070 and 2080ti
- GTX 1660
- Tesla T4
- Quadro RTX 6000, 8000

### Ampere

Introducr Tensor Cores 3.0(Append TF32, BF16 and FP64), Structured Sparsity(2:4), MIG, NVLink 3.0(600GB/s)

Representitive Products:

- A100(40GB/80GB HBM2e)
    - Cuda cores: 6912
    - Tensor cores: 432 (3.0)
    - NVLink 3.0
    - Memory bandwidth: 2039GB/s 
    - 312 TFLOPS(FP16)
    - 156 TFLOPS(TF32)
    - 624 TFLOPS(INT8 Sparse)
- RTX 3060, 3070, 3080
- RTX3090
    - CUDA cores: 10496
    - Tensore cores: 328
    - Memory: 24G
    - 285 TFLOPS(FP16)

### Hopper

Introduce Tensor COres 4.0(Append FP8), Transformer Engine(Dynamically switch FP8/FP16), NVLink 4.0(900GB/s), DPX, Tensor Memory Accelerator, Grace CPU

Representitive Products:

- H100(80GB HBM3)
    - Cuda cores: 18432
    - Tensor cores: 640(4.0)
    - NVLink 4.0
    - Memory Bandwidth: 3350GB/s
    - 1979 TFLOPS(FP8, Transformer Engine)
    - 990 TFLOPS(FP16)
    - 60 TFLOPS(FP64)
    - 3958 TOPS(INT8 Sparse)
- H200(141GB HBM3e)
    - Memory Bandwidth: 4800GB/s
    - 141GB HBM3e memory
    - Others are the same as H100
- Grace CPU
    - Traditional bottleneck: GPU-CPU communication
        - Intel/AMD CPU <- PCIe 5.0(128GB/s) -> NVIDIA GPU
    - NVLink-C2C(chip-to-chip)
        - Grace CPU <- NVLink-C2c(9000GB/s) -> Hopper GPU


### AdaLovelace

Introduce Tensor Cores 4.0(consumer grade), DLSS 3.0, RT Core 3.0, GDDR6X upgrade

Representitive Products:

- RTX 4070, 4080
- RTX 4090
    - Cuda Cores: 16384
    - Tensor Cores: 512 (4.0)
    - RT Core: 128
    - 24GB GDDR6X memory
    - 1008GB/s memory bandwidth
    - 661 TFLOPS(FP16 Sparse)
    - 83 TFLOP(FP32)
    - 1321 TOPS(INT8)
- RTX 6000 Ada
- L40s
    - Cuda Cores: 18176
    - Tensor Cores: 568 (4.0)
    - RT Cores: 142
    - 142 GDDR6X(with ECC) memory
    - 864GB/s memory bandwidth

### Blackwell

Introduce Tensor Cores 5.0(Append FP4/FP6), Transformer Engine 2.0, NVLink 5.0(1800GB/s), 2 GPU designs, Micro-Tensor scaling, DLSS 4.0

Representitive Products:

- B100
- B200(192GB HBM3e)
    - 2 GPU cips
    - Tensor Cores: Not release yet
    - Memory Bandwidth: 8000GB/s
    - NVLink 5.0
    - 18000 TFLOPS(FP4)
    - 9000 TFLOPS(FP8)
    - 4500 TFLOPS(FP16)
    - 72 PFLOPS(FP4, whole rack)
- GB200(Grace-Blackwell)
    - 1 Grace CPU(72 core ARM)
    - 2 B200 GPU
    - NVLink-C2C(900GB/s)
    - Whole memory: 192+480(CPU)
- RTX 5090
    - CUDA cores: 21760
    - Tensor Cores: 680 (5.0)
    - RT cores 170 (4.0)
    - 32G GDDR7 memory
    - Memory Bandwidth: 1792 GB/s
    - 3300 TOPS(FP4)
    - 900 TFLOPS(FP8)
    - DLSS 4.0
- RTX 5070, 5080

