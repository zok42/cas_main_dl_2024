# ZHAW CAS Machine Intelligence

# Module: Deep Learning (2024)


# Local Setup

    # Versions
	
	Python 3.10 		
	Tensorflow 2.16.1 	
	CUDA 12.3
	CUDNN 8.9.7
	skimage 0.24 		
	sklearn 1.5.2 		
	numpy 1.26.4 	

Official instructions to install Tensorflow: https://www.tensorflow.org/install/pip
	
	

# Setup Environment

## 1. Create env

    conda create -n cas_main_dl python=3.10
    conda activate cas_main_dl

## 2. Install Tensorflow

	# Either: GPU
	pip install tensorflow[and-cuda]==2.16.1
	# Or: CPU 
	pip install tensorflow==2.16.1

## 3. Other packages

	pip install notebook matplotlib pandas tqdm ipywidgets scikit-learn scikit-image
	
	
For detailed installation instructions, see https://www.tensorflow.org/install/pip


# Run directly in Colab

If you have forked the repository, you can run a notebook directly in Google Colab by using a link like this:

https://colab.research.google.com/github/(YOUR_GITHUB_ID)/cas_main_dl_2024/blob/master/01_mnist.ipynb

# Prepare Tensorflow with GPU on WSL2 (Windows Subsystem for Linux)

For Windows, it is recommended to install and use Tensorflow within WSL2 (Windows Subsystem for Linux).

	
Install WSL2, see https://docs.microsoft.com/windows/wsl/install

## GPU Support

To enable GPU support, one must also install CUDA Toolkit and CUDNN:

Good summary of needed steps: https://medium.com/@ali.abulhawa/installing-tensorflow-2-16-gpu-on-windows-wsl2-df73ac3446c9


### Install CUDA Toolkit
	
See https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_network

	wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.1-1_all.deb
	sudo dpkg -i cuda-keyring_1.1-1_all.deb
	sudo apt-get update
	sudo apt-get -y install cuda-toolkit-12-3

### Install CUDNN

	- download https://developer.nvidia.com/downloads/compute/cudnn/secure/8.9.7/local_installers/12.x/cudnn-local-repo-ubuntu2204-8.9.7.29_1.0-1_amd64.deb/

    - copy file to WSL home dir

	sudo dpkg -i cudnn-local-repo-ubuntu2204-8.9.7.29_1.0-1_amd64.deb
	sudo cp /var/cudnn-local-repo-ubuntu2204-8.9.7.29/cudnn-local-08A7D361-keyring.gpg /usr/share/keyrings/
	sudo apt-get update
	sudo apt-get install libcudnn8=8.9.7.29-1+cuda12.2
	