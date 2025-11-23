# Pytorch

Pytorch follows **imperative programming**. You can compile the model by using
`torch.jit.script`, which transforms python code into torchscript. The compiled model can be further optimized and run in an environment without a python interpreter, and you can save the whole model(code and parameters) to run on other platforms.

## Architecture

1. Frontend: Python
2. Pytorch C++ core
3. Backend: cuDNN, MKL
4. Hardware Interface Layer: CUDA runtime, CPU instructions
5. Computing Hardware: Nvidia GPU, CPU

Python Frontend thread will wait for the C++ backend thread to finish computing the result. One benefit of this design is that the Python frontend thread does not need to perform actual computation. Thus, there is little impact on the program's overall performance, regardless of Python's performance.

## Torch

- **torch.tensor()** - construct a tensor by supplying the exact values for each element by supplying python list containing numerical literals

- **torch.arange()** - return a 1-d tensor, with values from the interval `[start, end)` taken with common difference `step` beginning from start

- **torch.range()** - same as torhc.arange, except include end in values

- **torch.numel(x)** / **x.numel()** - return the total number of elements in the input tensor

- **torch.reshape(x,shape)** / **x.reshape(shape)** - Returns a tensor with the same data and number of elements as `input`, but with the specified shape

- **torch.zeros()** - Returns a tensor filled with the scalar value 0, with the shape defined by the variable argument `size`

- **torch.ones()** - Returns a tensor filled with the scalar value 1, with the shape defined by the variable argument `size`

- **torch.randn()** - Returns a tensor filled with random numbers from a normal distribution with mean 0 and variance 1 (also called the standard normal distribution)

- **torch.normal()** - same as randn(), except for customize mean and variance

- **torch.rand()** - Returns a tensor filled with random numbers from a uniform distribution on the interval [0,1)

- **torch.randint()** - Returns a tensor filled with random integers generated uniformly between `low` (inclusive) and `high` (exclusive)

- **torch.exp(x)** - Returns a new tensor with the exponential of the elements of the input tensor `input`

- **torch.cat()** - Concatenates the given sequence of tensors in `tensors` in the given dimension

- **torch.sum(x)** / **x.sum()** - Returns the sum of all elements in the `input` tensor

- **torch.t(x)** - Expects input to be <= 2-D tensor and transposes dimensions 0 and 1

- **torch.clone(x)** / **x.clone()** - Returns a copy of `input` by allocating new memory

- **torch.mean(x)** / **x.mean()** - Returns the mean value of all elements in the `input` tensor. Input must be floating point or complex

- **torch.cumsum(x,dim)** / **x.cumsum(dim)** - Returns the cumulative sum of elements of `input` in the dimension `dim`

- **torch.dot()** - Computes the dot product of two 1D tensors

- **torch.mv()** - Performs a matrix-vector product of the matrix `input` and the vector `vec`

- **torch.mul()** - Multiplies `input` by `other` by Hadamard Product

- **torch.matmul()** / **@** - Matrix product of two tensors

- **torch.mm** - same as torch.matmul, but without boardcast

- **torch.norm()** - Returns the matrix norm or vector norm of a given tensor. Find L2 norm

- **torch.abs(x).sum()** - Return L1 norm

- **torch.no_grad** - Context-manager that disables gradient calculation

- **torch.save** - Saves an object to a disk file

- **torch.load** - Loads an object saved with torch.save from a file

- **torch.squeeze(input)** - Returns a tensor with all specified dimensions of input of size 1 removed.


**Tips**:

1. To automatically infer one component of the shape, we can place a `-1` for the shape component that should be inferred automatically. In our case, instead of calling `x.reshape(3, 4)`, we could have equivalently called `x.reshape(-1, 4)` or `x.reshape(3, -1)`.
2. boardcasting
3. saving memory
	1. Running operations can cause new memory to be allocated to host results. For example, if we write `Y = X + Y`, we dereference the tensor that `Y` used to point to and instead point `Y` at the newly allocated memory.
	2. Fortunately, performing in-place operations is easy. We can assign the result of an operation to a previously allocated array `Y` by using slice notation: `Y[:] = <expression>`.
	3. conversion to other python objects:
		1. Converting to a NumPy tensor (`ndarray`), or vice versa, is easy. The torch tensor and NumPy array will share their underlying memory, and changing one through an in-place operation will also change the other.

## Torch.Tensor

- **Tensor.shape** - Returns the size of the `self` tensor

- **Tensor.T** - Returns a view of this tensor with its dimensions reversed

- **Tensor.size()** - Returns the size of the `self` tensor

- **Tensor.requires_grad** - Is `True` if gradients need to be computed for this Tensor, `False` otherwise

- **Tensor.requires_grad_** - Change if autograd should record operations on this tensor: sets this tensor's `requires_grad` attribute in-place

- **Tensor.grad** - This attribute is `None` by default and becomes a Tensor the first time a call to `backward()` computes gradients for `self`

- **Tensor.backward()** - Computes the gradient of current tensor wrt graph leaves

- **Tensor.detach()** - Returns a new Tensor, detached from the current graph. The result will never require gradient

## Torch.nn

- **Tensor.nn.Parameter** - A kind of Tensor that is to be considered a module parameter

## Torch.nn.Module

- **net.state_dict()** - Return a dictionary containing references to the whole state of the module

- **net.load_state_dict()** - Copy parameters and buffers from state_dict into this module and its descendants

## Torch.cuda

- **torch.cuda.is_available**: check if GPU is available
- **torch.cuda.get_device_name(0)**: Get names of GPU available
- **torch.cuda.synchronize** - Wait for all kernels in all streams on a CUDA device to complete.
