FROM registry.access.redhat.com/ubi9/ubi:9.5

MAINTAINER "Meet Jani <meet.jani@ibm.com>"

ENV HOME_DIR=${PWD}

RUN yum update -y && \
        yum install -y python312-devel.ppc64le gcc git && \
        python3 -m pip install --upgrade pip setuptools wheel && \
        python3 -m pip install cython pytest git+https://github.com/pytoolz/toolz.git && \
        git clone https://github.com/pytoolz/cytoolz && \
        cd cytoolz && \
        python3 setup.py build_ext --inplace --with-cython && \
        pip install -e .

CMD ["/bin/bash"]
