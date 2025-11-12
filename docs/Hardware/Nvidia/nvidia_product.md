# Nvidia Product Line Category

## Nvidia Hardware Terminology

See in this page: [Nvidia Hardware Terminology](nvidia_hardware_term.md)

## DGX series - AI super computer

It is a series that hardware, software and network all configured by Nvidia, and with Nvidia directly supports

- DGX A100:
    - 8 x A100(80GB) SXM
    - NVLink 3.0 + NVSwitch
    - 2 x AMD EPYC 7742(128 cores)
    - 640G VRAM
    - 2TB DDR4 RAM
    - 15T NVMe4 SSD
    - 8 * 200GB/s HDR InfiniBand/Ethernet
    - 5 PFLOPS(FP16)
    - DGX OS

- DGX H100:
    - 8 x H100(80GB) SXM5
    - NVLink 4.0 + NVSwitch
    - 2 x Intel Xeon Platinum 8480C (112核)
    - 640G VRAM
    - 2TB DDR5 RAM
    - 30T NVMe5 SSD
    - 8 * 400GB/s HDR InfiniBand
    - 5 PFLOPS(FP16)


- DGX H200:
    - 8 x H200(141GB) SXM5
    - NVLink 4.0 + NVSwitch
    - 2 x Intel Xeon Platinum 8480C (112核)
    - 1.1T VRAM
    - 2TB DDR5 RAM
    - 30T NVMe5 SSD
    - 8 * 400GB/s HDR InfiniBand
    - 5 PFLOPS(FP16)


- DGX B200
    - 8 x B200(192GB) HBM3e
    - 1.5T VRAM
    - 72 PFLOPS (FP4)

- DGX GB200
    - 72 x B200 GPU
    - 36 x Grace CPU
    - 12.8T HBM3e VRAM
    - 17 TB RAM

- DGX Station

    - DGX Station A100: 4 * A100(40GB) with PCIe
    - DGX Station(Blackwell): Based on GB300, 784GB Unified memory
    - DGX Spark: GB10 Grace Blackwell, 128GB Unified memory
    - 1 PFLOPS(FP4)

## HGX series - OEM GPU module

It is a series that Nvidia only supports motherboards and GPUs, but CPU, memory, storage, case and software need to support by OEM. It's 40%~60% cheaper than DGX

- HGX A100
- HGX H100
- HGX H200
- HGX B100
- HGX B200

The GPUs configurations is the same as DGX series by each of them, but other components will depending on the OEM.

## IGX series - Industrial edge AI

It is a series of reliability-first edge AI computing platform. Such as medical imaging, Industrial testing, Logistics automation

- Nvidia IGX T7000
- Nvidia IGX T5000
- Nvidia IGX Orin 700
- Nvidia IGX Orin 500

## MGX 

It is a modular reference architecture, not a series, a kind of design standard.

## OVX series - Omniverse super workstation

It is a GPU system optimized for 3D design and digital twins. Such as building design, autonomous driving simulation, movie special effects

- Single Node OVX: 8 * L40s
- OVX superPOD(32 nodes): 256 * L40s

## Nvidia Embedded System series

[Nvidia Embedded System Product Line Overview](nvidia_embedded_system.md)

## IGX vs AGX

AGX series:

- For developers and research
- Development board form factor
- Ease of use prioritized

IGX series:

- For industrial deployment
- Industrial chassis form factor
- Reliability prioritized
