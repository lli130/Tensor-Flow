# Tensor-Flow
#1 set up tensor in windows system first
#how to activate a new environment in anaconda python
#1 create an environment called “abc”
conda create –n abc python=3 anaconda
#set path before activate it
set PATH=D:\anaconda2\envs\abc\Scripts;D:\anaconda2\envs\abc;%PATH%
#activate the environment and get the prompt environment
Activate cc35
#download tensorflow-cpu in the new environment
python -m pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/windows/cpu/tensorflow-1.1.0-cp35-cp35m-win_amd64.whl

#based on tensorflow, a series of machine learning and deep learning tasks can be conducted.
