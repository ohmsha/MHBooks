# CuPyのインストール

- CuPy の公式HP　https://cupy.chainer.org/
- CuPyは，NVIDIAのGPU（グラフィックボード）を必須とします。

### Linux（Ubuntu, CentOS）へのインストール
   CuPy Documents   https://docs-cupy.chainer.org/  &rarr; "Installation Guide"を参照してください。

### Windows 10へのインストール （7/8は試していないので不明です）
Anacondaをインストールしている人は次が便利です。
```
> conda install cupy
```


これで，CuPyとCUDA Toolkitを一括してインストールします（実は，cuDNNも同時にインストールされます）。

CUDA Toolkit: https://developer.nvidia.com/cuda-toolkit

すでに，CUDA Toolkitがインストールされていても，condaが自動解決してくれます。
**参照：** anaconda  / packages / cupy　https://anaconda.org/anaconda/cupy


##### Anacondaをインストールしていない人は，

初めに，CUDA Toolkitをインストールします。このインストールは幾つかのWEBで説明されています。例えば，

- CUDA Toolkit 10.0 インストール手順　https://qiita.com/East_san/items/62adb216b0e6f801ae1d

エラーが生じたら，CUDA Toolkitのバージョンを変更してみてください。
　ただし，CuPyの公式サイトで述べているように，WindowsやmacOSの動作保証はされていないことを予め了承しておいてください。