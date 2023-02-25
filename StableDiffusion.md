## StabilityAI is Open and FREE - Stable Diffusion


## Install for Windows

https://www.youtube.com/watch?v=6MeJKnbv1ts


renamed:

```
"C:\ai\stable-diffusion-webui\models\Stable-diffusion\sd-v1-4.ckpt"
to:
"C:\ai\stable-diffusion-webui\models\Stable-diffusion\model.ckpt"
```

edit:
```
"C:\ai\stable-diffusion-webui\webui-user.bat"
set COMMANDLINE_ARGS= --opt-split-attention --precision full --no-half --medvram
```

Run it by:
* going to c:\ai\...\*.bat


## Install for Linux

### For command line

https://github.com/Stability-AI/stablediffusion

### 1 GIT clone
### 2 - create environment and activate
```
conda env create --ldm --file=environment.yaml

```
### 2 follow steps
```
conda install pytorch==1.12.1 torchvision==0.13.1 -c pytorch
pip install transformers==4.19.2 diffusers invisible-watermark
pip install -e .

export CUDA_HOME=/usr/local/cuda-11.4
conda install -c nvidia/label/cuda-11.4.0 cuda-nvcc
conda install -c conda-forge gcc
conda install -c conda-forge gxx_linux-64==9.5.0

cd ..
git clone https://github.com/facebookresearch/xformers.git
cd xformers
git submodule update --init --recursive
pip install -r requirements.txt
pip install -e .
cd ../stablediffusion
```
### 4 - Download .CKPT file
### 5 Run
```
python scripts/gradio/depth2img.py configs/stable-diffusion/v2-midas-inference.yaml <path-to-ckpt>
```
OR
```
streamlit run scripts/streamlit/depth2img.py configs/stable-diffusion/v2-midas-inference.yaml <path-to-ckpt>
```

### Graphical interface

https://github.com/invoke-ai/InvokeAI
