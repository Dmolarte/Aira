## Installation

macOS:
xcode-select --install
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
brew update
brew install openssl readline sqlite xz llvm
brew install pyenv

linuxOS:
sudo apt-get update  # Update package lists (Debian/Ubuntu)
sudo yum update      # Update package lists (CentOS/RHEL)

# Install common dependencies (Debian/Ubuntu)
sudo apt-get install -y build-essential libssl-dev zlib1g-dev libbz2-dev \
libreadline-dev libsqlite3-dev wget curl llvm libncurses5-dev \
libncursesw5-dev xz-utils tk-dev libffi-dev liblzma-dev

# Install common dependencies (CentOS/RHEL)
sudo yum groupinstall 'Development Tools'
sudo yum install -y openssl-devel bzip2-devel readline-devel sqlite-devel \
wget curl llvm ncurses-devel ncurses-compat-libs xz-utils tk-devel libffi-devel liblzma-devel

# Install pyenv
curl https://pyenv.run | bash

# Open Bash
~/.bashrc

'
export PYENV_ROOT="$HOME/.pyenv"
[[ -d $PYENV_ROOT/bin ]] && export PATH="$PYENV_ROOT/bin:$PATH"
eval "$(pyenv init - bash)"
eval "$(pyenv virtualenv-init -)"  # If you're using pyenv virtualenv
'

------------

# 1. Install pyenv
pyenv install 3.9.20

# 2. Set Python 3.9.20 globally
pyenv global 3.9.20

# 3. Pyenv install shell
pyenv init

# 4. Create a virtual environment
python -m venv myenv  # Use this (no need for "or python3 -m venv myenv")
<!-- python -m venv myenv  # Use this (no need for "or python3 -m venv myenv") -->
<!-- python3 -m venv myenv  # Or python -m venv myenv if that's your default Python -->

# 5. Activate the virtual environment (choose one depending on your shell):
source myenv/bin/activate

# 6. Install required packages
pip install --upgrade pip
pip install --no-cache-dir tensorflow==2.18.0
pip install cmake
pip install googletrans==4.0.0rc1 --no-deps
pip install shapely
pip install -r requirements.txt

# TROUBLESHOOTING TIPS

pip install --upgrade pip
pip install --upgrade llama-stack

pip uninstall tensorflow
pip install tensorflow-cpu

sudo apt update
sudo apt install -y libgl1

sudo apt update && sudo apt install -y libgl1



# 7. If the project is in a specific folder (Optional)
cd "path/to/project/folder"  # Replace with actual folder path

# 8. Run the Python script
python main.py