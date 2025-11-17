# Data Parallel

You need to make sure the model parallelism method is data parallelism. This is an old way to do data parallel in pytorch

[Learn what is model parallelism](model_parallelism.md)  


## Steps

Suppose we have 4 GPUs

- Step 1: GPU 0 scatters data and model
    - GPU 0 → GPU 1: copy model + 1/4 batch
    - GPU 0 → GPU 2: copy model + 1/4 batch
    - GPU 0 → GPU 3: copy model + 1/4 batch
- Step 2: Each GPU computes independently
    - GPU 0: forward + backward → gradient_0
    - GPU 1: forward + backward → gradient_1
    - GPU 2: forward + backward → gradient_2
    - GPU 3: forward + backward → gradient_3
- Step 3: All gradients sent back to GPU 0
    - GPU 1 → GPU 0: send gradient_1
    - GPU 2 → GPU 0: send gradient_2
    - GPU 3 → GPU 0: send gradient_3
- Step 4: GPU aggregates and updates
    - GPU 0: average gradients + update parameters
- Step 5: GPU 0 broadcasts new model
    - GPU 0 → GPU 1, 2, 3: updated parameters

This is an AllReduce step.

## Problems
 
- Assume the file size of the parameters in a
model is M.  
GPU0 is required to receive 3M of data.  
GPU0 is also required to send 3M of data.  
GPU0's bandwidth for both sending and receiving files is fully utilized, while GPU1, GPU2, and GPU3's bandwidth is not fully utilized (only 1/3 compared to GPU0).  
- Do Not support Muti-node Multi-GPUs

[Learn what is single-node multi-GPUs](single_node_multi_gpu.md)  
[Learn what is multi-node multi-gpus](multi_node_multi_gpu.md)
