# Install-TensorFlow-GPU-Anaconda

(base) C:\Windows\system32>conda install -c anaconda tensorflow-gpu
Collecting package metadata (current_repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: C:\ProgramData\Anaconda3

  added / updated specs:
    - tensorflow-gpu


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    _tflow_select-2.1.0        |              gpu           3 KB  anaconda
    ca-certificates-2019.8.28  |                0         165 KB  anaconda
    certifi-2019.9.11          |           py37_0         155 KB  anaconda
    conda-4.8.1                |           py37_0         3.0 MB  anaconda
    cudatoolkit-10.0.130       |                0       371.0 MB  anaconda
    cudnn-7.6.5                |       cuda10.0_0       226.5 MB  anaconda
    openssl-1.1.1d             |       he774522_2         5.7 MB  anaconda
    tensorflow-2.0.0           |gpu_py37h57d29ca_0           4 KB  anaconda
    tensorflow-base-2.0.0      |gpu_py37h390e234_0       242.6 MB  anaconda
    tensorflow-gpu-2.0.0       |       h0d30ee6_0           3 KB  anaconda
    ------------------------------------------------------------
                                           Total:       849.2 MB

The following NEW packages will be INSTALLED:

  cudatoolkit        anaconda/win-64::cudatoolkit-10.0.130-0
  cudnn              anaconda/win-64::cudnn-7.6.5-cuda10.0_0
  tensorflow-gpu     anaconda/win-64::tensorflow-gpu-2.0.0-h0d30ee6_0

The following packages will be SUPERSEDED by a higher-priority channel:

  _tflow_select          pkgs/main::_tflow_select-2.3.0-mkl --> anaconda::_tflow_select-2.1.0-gpu
  ca-certificates                                 pkgs/main --> anaconda
  certifi                                         pkgs/main --> anaconda
  conda                                           pkgs/main --> anaconda
  openssl                                         pkgs/main --> anaconda
  tensorflow         pkgs/main::tensorflow-2.0.0-mkl_py37h~ --> anaconda::tensorflow-2.0.0-gpu_py37h57d29ca_0
  tensorflow-base    pkgs/main::tensorflow-base-2.0.0-mkl_~ --> anaconda::tensorflow-base-2.0.0-gpu_py37h390e234_0


Proceed ([y]/n)? y


Downloading and Extracting Packages
ca-certificates-2019 | 165 KB    | ############################################################################ | 100%
certifi-2019.9.11    | 155 KB    | ############################################################################ | 100%
_tflow_select-2.1.0  | 3 KB      | ############################################################################ | 100%
tensorflow-base-2.0. | 242.6 MB  | ############################################################################ | 100%
tensorflow-2.0.0     | 4 KB      | ############################################################################ | 100%
cudnn-7.6.5          | 226.5 MB  | ############################################################################ | 100%
openssl-1.1.1d       | 5.7 MB    | ############################################################################ | 100%
tensorflow-gpu-2.0.0 | 3 KB      | ############################################################################ | 100%
conda-4.8.1          | 3.0 MB    | ############################################################################ | 100%
cudatoolkit-10.0.130 | 371.0 MB  | ############################################################################ | 100%
Preparing transaction: done
Verifying transaction: done
Executing transaction: done

C:\Windows\system32>set "KERAS_BACKEND="

C:\Windows\system32>python C:\ProgramData\Anaconda3\etc\keras\load_config.py  1>temp.txt

C:\Windows\system32>set /p KERAS_BACKEND= 0<temp.txt

C:\Windows\system32>del temp.txt

C:\Windows\system32>python -c "import keras"  1>nul 2>&1

C:\Windows\system32>if errorlevel 1 (
ver  1>nul
 set "KERAS_BACKEND=theano"
 python -c "import keras"  1>nul 2>&1
)
