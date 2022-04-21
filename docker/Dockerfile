FROM conda/miniconda3

RUN uname -a && cat /etc/issue && python -V && pip -V

RUN mkdir -p /tmp/setup && \
     apt-get update && \
     apt-get install -y --no-install-recommends \
         build-essential \
         gcc \
         git \
         python-dev \
         python-pip \
         python-setuptools \
         software-properties-common \
         wget \
     && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/MaurizioFD/RecSys2019_DeepLearning_Evaluation.git /home/rec_sys

WORKDIR /home/rec_sys

RUN pip install -r requirements.txt

RUN python run_compile_all_cython.py

# RUN python run_WWW_17_NeuMF.py

CMD ["/bin/bash"]