# Optimized TensorFlow Wheels

If you see similar messages when you start TensorFlow then these wheels are for you!

```
The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
```

## Introduction

The builds enable various performance flags targeting modern CPUs, including SIMD support (AVX2, SSE4, FMA).
If you have a CPU released after ~2013 then you'll likely benefit from these on e.g. data pre-processing.

Build also enables [XLA](https://www.tensorflow.org/xla/) - an Accelerated Linear Algebra domain-specific just-in-time compiler.

Additional compute capabilities (5.0, 6.1, 7.0, 7.5) are enabled, meaning the wheels should work well on a wide range of GPUS: from `GTX 7xx` to `RTX 20xx` families.

## Available Wheels

|TensorFlow|Python|CUDA|CuDNN|TensorRT|NCCL|Compute Capability|OS|Link|
|---:|---:|---:|---:|---:|---:|---:|:---:|:---:|
|2.1.0|3.8|10.2|7.6|7.0|2.5|5.0,6.1,7.0,7.5|Linux|[tensorflow-2.1.0-cp38-cp38-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v2.1.0/tensorflow-2.1.0-cp38-cp38-linux_x86_64.whl)|
|2.1.0|3.7|10.2|7.6|7.0|2.5|5.0,6.1,7.0,7.5|Linux|[tensorflow-2.1.0-cp37-cp37m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v2.1.0/tensorflow-2.1.0-cp37-cp37m-linux_x86_64.whl)|
|2.0.0|3.8|10.2|7.6|N/A|2.5|5.0,6.1,7.0|Linux|[tensorflow-2.0.0-cp38-cp38-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v2.0.0-py3.8/tensorflow-2.0.0-cp38-cp38-linux_x86_64.whl)|
|2.0.0|3.7|10.1|7.5|N/A|2.4|5.0,6.1,7.0|Linux|[tensorflow-2.0.0-cp37-cp37m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v2.0.0/tensorflow-2.0.0-cp37-cp37m-linux_x86_64.whl)|

## Installation

Assuming you have all the requirements, you can install the wheel directly via pip:

```
pip install https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v2.1.0/tensorflow-2.1.0-cp37-cp37m-linux_x86_64.whl
```
And verify the installation (notice no warning messages):

```
$ python
Python 3.8.0 | packaged by conda-forge | (default, Nov 22 2019, 19:11:38)
[GCC 7.3.0] :: Anaconda, Inc. on linux
>>> import tensorflow as tf
I tensorflow/stream_executor/platform/default/dso_loader.cc:44] Successfully opened dynamic library libcudart.so.10.2
>>> tf.__version__
'2.1.0'
>>> tf.executing_eagerly()
True
>>> tf.constant([123]) + tf.constant([321])
I tensorflow/stream_executor/platform/default/dso_loader.cc:44] Successfully opened dynamic library libcuda.so.1
...
I tensorflow/stream_executor/platform/default/dso_loader.cc:44] Successfully opened dynamic library libcudnn.so.7
I tensorflow/core/common_runtime/gpu/gpu_device.cc:1241] Created TensorFlow device (...) -> physical GPU (...)
<tf.Tensor: shape=(1,), dtype=int32, numpy=array([444], dtype=int32)>
```

## Benchmark

The wheels are benchmarked by training an MNIST model from [TF Models](https://github.com/tensorflow/models) on a CPU. Results for TF 2.1 are as follows:

| Build / Time Per Epoch |Mean|Min|Max|
|---:|---:|---:|---:|
| Official  | 16.7s | 16s | 19s |
| Optimized | 14.3s | 12s | 17s |

## Requests

If you need a different TensorFlow / CUDA / CuDNN / Python combination feel free to open a GitHub ticket.
