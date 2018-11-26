# Optimized TensorFlow Wheels

If you see similar messages when you start TensorFlow then these wheels are for you!

```
The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
```
## Available wheels
|TF|HW|OS|Compute Capability|Python|CUDA|CuDNN|NCCL|Link|
|---|---|---|---|---|---|---|---|---|
|1.12|GPU+CPU|Linux|6.1|3.6|10.0|7.3|2.3|[https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.12.0/tensorflow-1.12.0-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.12.0/tensorflow-1.12.0-cp36-cp36m-linux_x86_64.whl)|
|1.11|GPU+CPU|Linux|6.1|3.6|10.0|7.3|2.3|[https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.11.0/tensorflow-1.11.0-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.11.0/tensorflow-1.11.0-cp36-cp36m-linux_x86_64.whl)|
|1.10|GPU+CPU|Linux|6.1|3.6|9.2|7.2|2.2|[https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.10.0/tensorflow-1.10.0-cp36-cp36m-linux_x86_64.whl](https://github.com/inoryy/tensorflow-optimized-wheels/releases/download/v1.10.0/tensorflow-1.10.0-cp36-cp36m-linux_x86_64.whl)|


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
