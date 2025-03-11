FROM nvidia/cuda:12.1.0-cudnn8-devel-ubuntu22.04

# Set environment variables
ENV DEBIAN_FRONTEND=noninteractive
ENV PYTHONUNBUFFERED=1
ENV PATH="/opt/conda/bin:${PATH}"

# Install system dependencies
RUN apt-get update && apt-get install -y \
    git \
    wget \
    curl \
    build-essential \
    ca-certificates \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# Install Miniconda
RUN wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O /tmp/miniconda.sh \
    && bash /tmp/miniconda.sh -b -p /opt/conda \
    && rm /tmp/miniconda.sh \
    && conda clean -afy

# Create conda environment with Python 3.11
RUN conda create -n evo2 python=3.11 -y \
    && conda clean -afy
ENV PATH="/opt/conda/envs/evo2/bin:${PATH}"
SHELL ["/bin/bash", "-c"]

# Clone Evo 2 repo
WORKDIR /app
RUN git clone --depth 1 --recurse-submodules --shallow-submodules https://github.com/ArcInstitute/evo2.git
WORKDIR /app/evo2

# For development/testing - Install dependencies without building extensions first
RUN source activate evo2 \
    && pip install -e . --no-build-isolation --no-deps \
    && conda clean -afy \
    && rm -rf ~/.cache/pip

# Create entrypoint script explicitly with correct line endings
RUN echo '#!/bin/bash' > /entrypoint.sh \
    && echo 'source activate evo2' >> /entrypoint.sh \
    && echo 'exec "$@"' >> /entrypoint.sh \
    && chmod +x /entrypoint.sh \
    && cat /entrypoint.sh  # Verify content

# Set entrypoint
ENTRYPOINT ["/entrypoint.sh"]

# Default command to run tests
CMD ["python", "-c", "import torch; print(f'PyTorch version: {torch.__version__}'); print(f'CUDA available: {torch.cuda.is_available()}')"]
