## Install

1. Clone this repository and navigate to LLaVA folder

```
git clone https://github.com/haotian-liu/LLaVA.git
cd LLaVA
```



2. Install Package

```
conda create -n llava python=3.10 -y
conda activate llava
pip install --upgrade pip  # enable PEP 660 support
pip install -e .
```

![image-20241228034456771](LLAVA代码运行记录.assets/image-20241228034456771.png)

![image-20241228034518764](LLAVA代码运行记录.assets/image-20241228034518764.png)

<img src="LLAVA代码运行记录.assets/image-20241228034534431.png" alt="image-20241228034534431" style="zoom:50%;" />



3. Install additional packages for training cases

```
pip install -e ".[train]"
pip install flash-attn --no-build-isolation
```



### Upgrade to latest code base

```
git pull
pip install -e .

# if you see some import errors when you upgrade,
# please try running the command below (without #)
# pip install flash-attn --no-build-isolation --no-cache-dir
```