# Distributed Data Parallel

[Learn waht is Data Parallel](data_parallel.md)

This is the modern pytorch method to do data parallel. which is a ring synchronization method. [NCCL](../Tools/Nvidia/nccl.md) provides good optimization for DDP.


## Steps:

- Assume we have 4 nodes

1. Broke the gradients into n chunks
2. and then doing steps below
![ddp](/images/ddp.png)
3. Untile every GPU's n chunks has four red cross.

- Then the total time improve from DP's n to (n-1)/n which is 1

- This is an Ring-AllReduce step.
- Support Multi-node well


[Learn what is single-node multi-GPUs](single_node_multi_gpu.md)  
[Learn what is multi-node multi-gpus](multi_node_multi_gpu.md)
