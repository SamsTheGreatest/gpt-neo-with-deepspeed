# gpt-neo-with-deepspeed
Exploring DeepSpeed hanging while training

Running on Tesla T4

Installed latest torch via:
`conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia`

Installed deepspeed via:
`pip install transformers[deepspeed]`

All dependencies listed in requirements.txt

ds_report:
```
--------------------------------------------------
DeepSpeed C++/CUDA extension op report
--------------------------------------------------
NOTE: Ops not installed will be just-in-time (JIT) compiled at
      runtime if needed. Op compatibility means that your system
      meet the required dependencies to JIT install the op.
--------------------------------------------------
JIT compiled ops requires ninja
ninja .................. [OKAY]
--------------------------------------------------
op name ................ installed .. compatible
--------------------------------------------------
cpu_adam ............... [NO] ....... [OKAY]
fused_adam ............. [NO] ....... [OKAY]
fused_lamb ............. [NO] ....... [OKAY]
sparse_attn ............ [NO] ....... [OKAY]
transformer ............ [NO] ....... [OKAY]
stochastic_transformer . [NO] ....... [OKAY]
 [WARNING]  async_io requires the libraries: ['libaio-dev'] but are missing. Can be fixed by: `apt install libaio-dev`.
async_io ............... [NO] ....... [NO]
transformer_inference .. [NO] ....... [OKAY]
utils .................. [NO] ....... [OKAY]
quantizer .............. [NO] ....... [OKAY]
--------------------------------------------------
DeepSpeed general environment info:
torch install path ............... ['/home/jovyan/anaconda3/envs/username/lib/python3.7/site-packages/torch']
torch version .................... 1.9.0
torch cuda version ............... 11.1
nvcc version ..................... 10.1
deepspeed install path ........... ['/home/jovyan/anaconda3/envs/username/lib/python3.7/site-packages/deepspeed']
deepspeed info ................... 0.4.1, unknown, unknown
deepspeed wheel compiled w. ...... torch 1.9, cuda 11.1
```


```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 450.102.04   Driver Version: 450.102.04   CUDA Version: 11.0     |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  Tesla T4            Off  | 00000000:04:00.0 Off |                    0 |
| N/A   53C    P8    10W /  70W |      0MiB / 15109MiB |      0%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+
```
