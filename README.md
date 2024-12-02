# ubuntu_24.04_pytorch_rocm_rx6800_instructions
Instructions on how to build pytorch for rocm on ubuntu 24.04, for an rx6800. This would also apply for other amd cards not directly supported by the first-party pytorch .whl's. Pre-requisite is that you have installed ROCM.
1. Clone https://github.com/pytorch/pytorch
2. Find your LLVM target using: https://llvm.org/docs/AMDGPUUsage.html. This is your GPU Architecture. In my situation with an RX 6800, that is `gfx1030`.
3. Specify your GPU architecture by setting the environment variable `PYTORCH_ROCM_ARCH`
4. Build Pytorch from scratch - following the conda instructions, with one exception. Use `python setup.py bdist_wheel` to build the `.whl`, the default instructions are to install for development.
