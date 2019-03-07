# Optimized TensorFlow Wheels

If you see similar messages when you start TensorFlow then these wheels are for you!

```
The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
```

## Introduction

The builds enable CPU optimizations such as `SSE4`, `AVX2`, and `FMA`. If you have a CPU released after ~2013 then you'll benefit from them. Note that you will benefit from these even if you do all your training on GPU due to i/o pipeline optimizations. I think I've gained about 10-15% performance boost even on most straightforward supervised learning tasks. And of course in CPU only setting they give significant improvement, sometimes matching GPU speeds on smaller neural networks (especially true for laptops where even in higher end models GPUs tend to lag behind).

Additionally, build enables [XLA](https://www.tensorflow.org/xla/) - an Accelerated Linear Algebra domain-specific just-in-time compiler, and [MPI](https://github.com/tensorflow/tensorflow/tree/master/tensorflow/contrib/mpi) - a faster way to run distributed TensorFlow than what is offered built-in.

## Available Wheels
|TensorFlow|CUDA|CuDNN|Python|NCCL|Compute Capability|OS|Link|
|---:|---:|---:|---:|---:|---:|---:|:---:|
|1.13.1|10.0|7.3|3.6|2.3|5.0, 6.1, 7.0|Linux|[tensorflow-1.13.1-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.13.1/tensorflow-1.13.1-cp36-cp36m-linux_x86_64.whl)|
|1.12.0|10.0|7.3|3.6|2.3|5.0, 6.1, 7.0|Linux|[tensorflow-1.12.0-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.12.0/tensorflow-1.12.0-cp36-cp36m-linux_x86_64.whl)|
|1.11.0|10.0|7.3|3.6|2.3|6.1|Linux|[tensorflow-1.11.0-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.11.0/tensorflow-1.11.0-cp36-cp36m-linux_x86_64.whl)|
|1.10.0|9.2|7.2|3.6|2.2|6.1|Linux|[tensorflow-1.10.0-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.10.0/tensorflow-1.10.0-cp36-cp36m-linux_x86_64.whl)|


## Installation

Assuming you have all the requirements, you can install the wheel directly via pip:

```
pip install https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.12.0/tensorflow-1.12.0-cp36-cp36m-linux_x86_64.whl
```
And verify the installation (notice no warning messages):

```
python
Python 3.6.6 |Anaconda, Inc.| (default, Oct  9 2018, 12:34:16) 
[GCC 7.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
>>> tf.__version__
'1.12.0'
```

## Requests

If you need a different TensorFlow / CUDA / CuDNN / Python combination feel free to open a GitHub ticket.
