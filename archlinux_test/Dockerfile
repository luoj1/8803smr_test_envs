FROM library/archlinux:latest
RUN yes | pacman -Sy git python python-pip clang
RUN pip install astunparse numpy ninja pyyaml setuptools cmake cffi typing_extensions future six requests dataclasses && cd home && git clone https://github.com/pytorch/pytorch.git 
RUN cd /home/pytorch/ && export BUILD_CAFFE2=0 BUILD_CAFFE2_OPS=0 BUILD_TEST=0 USE_FBGEMM=0 && python setup.py develop
RUN python -c 'import torch; print(torch.__version__)'
##TODO: create a experiment repo and clone our test to built image?
##TODO: login into built image, pull the changes on pytorch, rebuild by 'pip setup.py:' and run experiment

