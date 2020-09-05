# PyMC3のインストール
HP: https://docs.pymc.io/


```
> conda install -c conda-forge pymc3

```
または
```
> pip install pymc3
```
ただし，PyMC3はC/C++コンパイラ（64ビット版）を使うため，次の実行
```
import pymc3

sorry, unimplemented: 64-bit mode not compiled in
```
このエラーが生じたならば，ユーザー所有のPCのC/C++コンパイラが32ビット版である可能性があります。
これを64ビット版に変更（再インストール）してください。

例えば，MinGWがインストールされているとします：http://www.mingw.org/

このバージョンを調べます。
```
> gcc -v
・・・・
Target: mingw32
・・・・・
Thread model: win32
gcc version 4.8.1 (GCC)
```
win32の表示は，32ビット版を示しています。

これを削除します。この仕方は次を参照

https://achapi2718.blogspot.com/2018/04/mingw-windows10.html


MinGW-w64のインストールは次を参照

https://www.javadrive.jp/cstart/install/index6.html


参考：ダウンロードサイト mingw-w64 GCC for Windows 64 & 32 bits

http://mingw-w64.org/

以上