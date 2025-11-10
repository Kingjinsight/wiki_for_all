# Jetson

**Always check your JetPack version first** - Jetson runs on ARM architecture, so NVIDIA only provides specific framework versions for each JetPack release.

## The TorchVision Problem

NVIDIA provides PyTorch for Jetson, but **not TorchVision**. If you try compiling TorchVision from source, you'll likely hit:

```
RuntimeError: operator torchvision::nms does not exist
```

### Solution  
Use pre-compiled torchvision that provided by ultralytics.   
Firstly, check your

- Python version
- PyTorch version
- JetPack version

Then, find matches torchvision from [Ultralytics releases](https://github.com/ultralytics/assets/releases)
f

