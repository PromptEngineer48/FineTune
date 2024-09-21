1.	For Setting up Ubuntu: Turn on Windows System for Linux from the features
2.	Open powershell and type “wsl --install”
3.	Navigate to \\wsl.localhost\Ubuntu\home\asus and create a folder to work on.
4.	Next is Installing Visual Studio Code for Ubuntu. Go to VS Code Editor and download the Debian version.
5.	Place the executable file in the Downloads of Windows.
6.	Now, in order to access the download folder, go to ubuntu cli and type ls /mnt/c/Users/Asus/Downloads 
7.	Try to install using the following command: sudo dpkg -i /mnt/c/Users/Asus/Downloads/code_1.93.1-1726079302_amd64.deb
8.	You will fail. But then run these, sudo apt update and sudo apt install -f and then try reinstalling.
9.	Congrats, now go to start and open the visual studio code editor ubuntu version. 
10.	Do the initial settings.
11.	Next would be to install miniconda. Using the following command
a.	# ## Prerequisite. Run on Terminal. Install miniconda. In the folder cd /home/asus/
b.	mkdir -p ~/miniconda3
c.	wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
d.	bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
e.	rm -rf ~/miniconda3/miniconda.sh
f.	~/miniconda3/bin/conda init bash
g.	~/miniconda3/bin/conda init zsh
12.	Next would be set up a virtual environment 
a.	### Run on Terminal 
b.	conda create --name unsloth_env python=3.11 pytorch-cuda=12.1 pytorch cudatoolkit xformers -c pytorch -c nvidia -c xformers -y
c.	conda activate unsloth_env
d.	pip install "unsloth[colab-new] @ git+https://github.com/unslothai/unsloth.git"
e.	pip install --no-deps trl peft accelerate bitsandbytes
13.	As a last step, do, conda install jupyter
14.	Now, get the files ready, and train the model. While training, there will be another issue of C compiler not found. You solve this by running these two:
a.	sudo apt update
b.	sudo apt install build-essential
15.	Next would be to save the models as safe tensors
16.	Next would be save in the .gguf format
17.	This would be used to make the ollama model
18.	Next, install the Ollama library using the command on terminal “curl -fsSL https://ollama.com/install.sh | sh”
19.	Create the Modelfile and run the ollama command to create the model using the Modelfile
