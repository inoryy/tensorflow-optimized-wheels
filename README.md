# Optimized TensorFlow Wheels

If you similar messages when you start TensorFlow then these wheels are for you!

```
The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
```
## Available wheels
|TF|Arch|Python|CUDA|CuDNN|NCCL|Link|
|---|---|---|---|---|---|---|
|1.10|GPU+CPU|3.6|9.2|7.2|2.2|[https://github.com/inoryy/tensorflow-optimized-wheels/releases/tag/v1.10.0](https://github.com/inoryy/tensorflow-optimized-wheels/releases/tag/v1.10.0)|

## Installation

Assuming you have all the requirements, you can install the wheel directly via pip:

```
pip install https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.10.0/tensorflow-1.10.0-cp36-cp36m-linux_x86_64.whl
```
And verify the installation (notice no warning messages):

```
python
Python 3.6.5 |Anaconda, Inc.| (default, Apr 29 2018, 16:14:56) 
[GCC 7.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
>>> print(tf.__version__)
1.10.0
```
