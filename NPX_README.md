**INSTRUCTIONS FOR MACOS ONLY**
PRE-PRE-REQ

- We need C++ compiler
  xcode-select --install
  brew install gcc
- To run on GPU, build llama.cpp with Metal :)
  `https://github.com/ggerganov/llama.cpp`
- in root dir
  git clone https://github.com/ggerganov/llama.cpp
  cd llama.cpp
  make
- On MacOS, Metal is enabled by default. Using Metal makes the computation run on the GPU. To disable the Metal build at compile time use the LLAMA_NO_METAL=1 flag or the LLAMA_METAL=OFF cmake option.
  PRE-REQ
- Then in NPXAI-PRIVATEGPT dir
  `https://github.com/pyenv/pyenv`
  brew update
  brew install pyenv
  pyenv --version
  pyenv install 3.11
  pyenv local 3.11
  `https://python-poetry.org/docs/#installing-with-the-official-installer`
  curl -sSL https://install.python-poetry.org | python3 -
  poetry --version
  poetry install --with ui
  poetry install --with local
  poetry run python scripts/setup
- if running on GPU, make sure that llama.cpp is built with Metal
  CMAKE_ARGS="-DLLAMA_METAL=on" pip install --force-reinstall --no-cache-dir llama-cpp-python
- see the `Makefile` for other commands :)
  make run
  or
  poetry run python -m private_gpt
