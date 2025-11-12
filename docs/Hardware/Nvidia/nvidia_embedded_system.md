# Nvidia Embedded System

## Nvidia Hardware Terminology

See in this page: [Nvidia Hardware Terminology](nvidia_hardware_term.md)

## Jetson series
It is an edge AI computing platform, within development board form.

- Jetson Nano: for beginner
    - 128 cuda core
    - 4 core ARM CPU
    - 4GB  RAM
    - 0.5 TOPS(FP16)
    - JetPack 4.6(Ubuntu 18.04)
    - CUDA 10.2
    - TensorRT7
- Jetson Orin Nano: for small projects
    - 1024 cuda cores
    - 32 tensor cores
    - 6 core ARM CPU
    - 8GB RAM
    - 67 TOPS
    - JetPack6(Ubuntu 22.04)
    - CUDA 12.2
    - TensorRT 8.6
    - Pytorch 2.0, TensorFlow 2.x
- Jetson Orin NX:
    - 1024 cuda cores
    - 64 tensor coresB RAM
    - 100 TOPS
- Jetson AGX Orin
    - 2048 cuda cores
    - 64 tensor cores
    - 12 core ARM CPU
    - 275 TOPS
- Jetson AGX Thor
    - 2560 cuda cores
    - 96 tensor cores
    - 14 core ARM CPU
    - 2070 TFLOPS(FP4 Sparse)


## Drive AGX
NVIDIA DRIVE AGX gives you a scalable and energy-efficient AI computing platform designed to process the complex workloads required for autonomous driving.

### Hardware

- Nvidia Drive AGX Hyperion 10
    - 2 x Drive AGX Thor
    - Features 14 high-definition cameras, 9 radars, 1 lidar, and 12 ultrasonic sensors and a microphone array.
    - Includes DRIVE™ AV software, purpose-built for L4 autonomy.
- Nvidia Drive AGX Thor
    - Delivers more than 1,000 INT8 TOPS (2,000 FP4 FLOPs).
    - Offers a scalable architecture supporting Level 2+ to fully autonomous driving.
    - Provides superior safety, with ASIL-D compliance and redundancy.
- Nvidia Drive AGX Orin
    - Delivers up to 254 TOPS of AI performance.
    - Offers a scalable architecture supporting Level 2+ to fully autonomous driving.
    - Provides superior safety, with ASIL-D compliance and redundancy

### Software

- Nvidia DriveOS
- Nvidia Drive AV

## Clara AGX: AI for Medical Devices and Robotics
