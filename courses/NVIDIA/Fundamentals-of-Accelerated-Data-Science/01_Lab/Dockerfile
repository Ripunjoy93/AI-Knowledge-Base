# FROM nvcr.io/nvidia/rapidsai/rapidsai:23.06-cuda11.2-runtime-ubuntu20.04-py3.9
# FROM nvcr.io/nvidia/rapidsai/base:24.10a-cuda12.0-py3.10
FROM rapidsai/base:24.10a-cuda12.0-py3.10
# FROM nvcr.io/nvidia/rapids-pb24h1:24.02.03-runtime
# Fix CUDA repository key
# no longer needed for public repo
# RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/3bf863cc.pub
# RUN apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64/7fa2af80.pub

USER root

RUN apt-get update -y
RUN apt-get install -y graphviz
RUN apt install -y libb64-dev
# RUN pip install jupyterlab graphviz
RUN conda install -c conda-forge jupyterlab
# RUN jupyter labextension install @pyviz/jupyterlab_pyviz
# RUN jupyter labextension install @bokeh/jupyter_bokeh
# RUN pip install pyviz
RUN pip install graphviz

# Install Triton
RUN pip install tritonclient[all]==2.49.0

# RUN pip install cupy-cuda12x
# RUN conda install -c conda-forge cupy

# RUN pip install polars[gpu] --no-deps --extra-index-url=https://pypi.nvidia.com
# RUN pip install polars[gpu] --extra-index-url=https://pypi.nvidia.com

# RUN pip install nx-cugraph-cu12 --extra-index-url https://pypi.anaconda.org/rapidsai-wheels-nightly/simple

# Install system-level graphviz...
# RUN conda run -n rapids apt-get update -y
# RUN conda run -n rapids apt-get install -y graphviz

# ... and python library graphviz, both for Dask visualizations
# RUN conda run -n rapids pip install graphviz

# Create working directory to add repo.
WORKDIR /dli

# Load contents into student working directory.
ADD . .

# Create working directory for students.
WORKDIR /dli/task

# Copy a jupyterlab workspace into the image to set initial jupyter lab view. See `set-landing` for details.
COPY jupyter/ /root/.jupyter

# Jupyter listens on 8888.
EXPOSE 8888

# Please see `entrypoint.sh` for details on how this content
# is launched.
ADD entrypoint.sh /usr/local/bin
ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]
