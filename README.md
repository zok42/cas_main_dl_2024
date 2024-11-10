# ZHAW CAS Machine Intelligence

# Module: Deep Learning (2024)


# Local Setup

    # Versions
	Python 3.10 		# 3.9
	Tensorflow 2.17.0 	# 2.8.2
	CUDA 12.3
	CUDNN 8.9.7
	skimage 0.24 		# < 0.19
	sklearn 1.5.2 		# < 1.0.0
	numpy 1.26.4 		# < 1.23

	# se https://www.tensorflow.org/install
	# on windows, must use WSL2
	
	Install WSL2, see https://docs.microsoft.com/windows/wsl/install
	
	Install CUDA Toolkit and cudnn, see https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=WSL-Ubuntu&target_version=2.0&target_type=deb_network
	wget https://developer.download.nvidia.com/compute/cuda/repos/wsl-ubuntu/x86_64/cuda-keyring_1.1-1_all.deb
	sudo dpkg -i cuda-keyring_1.1-1_all.deb
	sudo apt-get update
	sudo apt-get -y install cuda-toolkit-12-3

	Install CUDNN
	https://medium.com/@ali.abulhawa/installing-tensorflow-2-16-gpu-on-windows-wsl2-df73ac3446c9

	- download https://developer.nvidia.com/downloads/compute/cudnn/secure/8.9.7/local_installers/12.x/cudnn-local-repo-ubuntu2204-8.9.7.29_1.0-1_amd64.deb/

    - copy file to WSL home dir

	sudo dpkg -i cudnn-local-repo-ubuntu2204-8.9.7.29_1.0-1_amd64.deb
	sudo cp /var/cudnn-local-repo-ubuntu2204-8.9.7.29/cudnn-local-08A7D361-keyring.gpg /usr/share/keyrings/
	sudo apt-get update
	sudo apt-get install libcudnn8=8.9.7.29-1+cuda12.2
	
	

    # 1. create env
    conda create -n cas_main_dl python=3.10
    conda activate cas_main_dl

	# 2. install tensorflow and other stuff
	# gpu
	pip install tensorflow[and-cuda]==2.16.1
	# cpu 
	pip install tensorflow==2.16.1
	# extra packages
	pip install notebook matplotlib pandas tqdm ipywidgets scikit-learn scikit-image
	
	
	
	

For detailed installation instructions, see https://www.tensorflow.org/install/pip






	# 2. install CUDA (if GPU available)
	# a) Windows
	conda install -c conda-forge cudatoolkit=11.2 cudnn=8.1.0
	# b) Linux
	conda install -y -c conda-forge cudatoolkit=11.2.2 
	pip install nvidia-cudnn-cu11

    # 3. install tensorflow
    pip install tensorflow==2.17.0 tensorflow-datasets 'tensorflow-addons==0.18.0'

	# 4. install extra libs
	pip install matplotlib "scikit-learn<1.0.0" pandas tqdm "scikit-image<0.19" "numpy<1.23.0"  wget notebook ipywidgets
	
	


# Run directly in Colab

If you have cloned the repository, you can run a notebook directly in Google Colab by using a link like this:

https://colab.research.google.com/github/(YOUR_GITHUB_ID)/cas_main_dl_2023/blob/master/01_mnist.ipynb

