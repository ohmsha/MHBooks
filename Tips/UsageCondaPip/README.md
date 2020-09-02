# condanとpipの使い方
#### condaとpipの違いに関心のある読者の方へ
Anaconda環境では，なるべくcondaコマンドで様々な操作を行うことを勧めます。
condaとpipの混合操作は依存関係やパッケージ削除などで混乱が生じる可能性があります。
ただ，pipでインストールせざるを得ないパッケージもあり，このインストール方法も説明します。


#### 目次
1. Getting started
2. パッケージの管理
3. Pythonの異なるバージョンの仮想環境作成
4. pipの使い方

----------------

## 1. Getting Started

初めに，Anacondaのインストールと環境設定が完了していること。
Anacondaが存在するパスは次である。（Windows10の場合，他のOSは他書を参照）。

- [All Users]でインストールした場合
     C:\ProgramData\Anaconda3
- [Just Me]でインストールした場合
     C:\Users\user_name\Anaconda3

condaコマンドのドキュメント類は次にある。

- Conda HP: https://conda.io/
- Full documentation: https://conda.io/docs/.
- Getting Started:  https://conda.io/docs/user-guide/getting-started.html
- Managing packages https://conda.io/docs/user-guide/tasks/manage-pkgs.html 
- Command reference （コマンドオプションなど）:  https://conda.io/docs/commands.html

なお，ここの説明ではWindowsのコマンドプロンプト（またはPowerShell）内でのコマンド操作を次のプロンプト（”>”）を用いて行っているものとする。

    > command


#### バージョンを見る
    > conda --version

#### アップデート 
Anacondaのアップデートは、管理者権限でコマンドプロンプトを起動し、次のようにする。

    > conda update conda
 	Proceed ([y]/n)? y

または

    > conda update --all

#### Anacondaの環境表示

    > conda info -e  

\# conda environments:  
\#  
base      *  C:\ProgramData\Anaconda3  

もし，Anaconda仮想環境で Pythonの他のバージョンを作成していれば，その情報が上記に現れる。

--------------------------------
## 2. パッケージの管理

インストール済みのパッケージリスト表示

    > conda list

    > conda list numpy
    
    > conda list --export > env.txt

Anacondaが含むパッケージは，次のサイトで対応するOSをクリックすると見られる。
https://docs.anaconda.com/anaconda/packages/pkg-docs

Rのパッケージの幾つかのリストが次にある。  
https://docs.anaconda.com/anaconda/packages/r-language-pkg-docs

これらも，Anacondaパッケージと同様にしてインストールできる。ただし，環境構築用のパッケージもあり，これらは別の注意を必要とするので，各自で調べること。

