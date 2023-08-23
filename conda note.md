# day3 -善 Bio tech 入门笔记

Cona in a nutshell

- An App store-like software,
- Miniconda = conda+python+base packages
- Anacona =  Miniconda + 150 other packages

Installation

- **uname -a**  to check how many bits your system is
- 清华mirror [https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/)
- **cd** to the working dir
- **wget** the url to that miniconda package
- **bash** the .sh file you just downloaded
- **source ~/.bashrc** activate conda

Conada

- 使用Conda安装软件包时，它会从channels中查找这些软件包。
    - 默认的通道是defaults，但有时候需要从其他channel安装软件包，ex：conda-forge、bioconda。
    - 使用conda config --add channels可以将新的通道添加到搜索列表的**顶部**。Conda将**首先**在这些新添加的通道中查找软件包
    - channel的搜索顺序：不同的通道包含不同版本的相同软件包。因此要将**最常用**或**最受信任的通道**添加到列表的顶部
    - 使用中科大的镜像
        - **conda config --add channels [https://mirrors.bfsu.edu.cn/anaconda/cloud/bioconda/](https://mirrors.bfsu.edu.cn/anaconda/cloud/bioconda/)**
        - **conda config --add channels [https://mirrors.bfsu.edu.cn/anaconda/cloud/conda-forge/](https://mirrors.bfsu.edu.cn/anaconda/cloud/conda-forge/)**
        - **conda config --add channels [https://mirrors.bfsu.edu.cn/anaconda/pkgs/free/](https://mirrors.bfsu.edu.cn/anaconda/pkgs/free/)**
        - **conda config --add channels [https://mirrors.bfsu.edu.cn/anaconda/pkgs/main/](https://mirrors.bfsu.edu.cn/anaconda/pkgs/main/)**
- **conda config** --set show_channel_urls yes
    - 在安装、更新packages时显示channel URL，可以看到每个软件包是从哪个通道安装的。
- **conda list** check all the packages
- **conda install fastqc -y**
- **conda remove fastqc -y**
- **conda create --name myenv python=3.7**创建一个新的Conda环境
- **conda activate myenv** 激活
- **conda deactivate**
- **conda env remove --name myenv**
- **conda env export > environment.yml**
- **conda env create -f environment.yml**
- tips from stackoverflow: Don't use the base environment for all your projects, or at all
