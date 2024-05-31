# ml-env-setup for windows

Download these

```Shell
https://aka.ms/vs/16/release/vc_redist.x64.exe
```

```Shell
https://developer.nvidia.com/compute/cuda/10.1/Prod/local_installers/cuda_10.1.105_418.96_win10.exe
```

```Shell
https://developer.nvidia.com/compute/machine-learning/cudnn/secure/7.6.5.32/Production/10.1_20191031/cudnn-10.1-windows10-x64-v7.6.5.32.zip
```

Then

```Shell
conda create -n tf_gpu python=3.6
```

```Shell
conda activate tf_gpu
```

```Shell
pip install ipykernel
```

```Shell
python -m ipykernel install --user --name tf_gpu --display-name "tf_gpu"
```

```Shell
nvcc -V
```

```Shell
conda search cudnn
```

```Shell
conda install cudnn=7.6.5=cuda10.1_0
```

## for tensorflow

```Shell
pip install tensorflow-gpu
```

## for pytorch

```Shell
pip install torch==1.4.0 torchvision==0.5.0 -f https://download.pytorch.org/whl/cu101/torch_stable.html
```

or

```Shell
pip install torch_nightly -f https://download.pytorch.org/whl/nightly/cu90/torch_nightly.html
```

backup env list

```Shell
conda env export > environment.yml
```

```Shell
conda env create -f environment.yml
```
