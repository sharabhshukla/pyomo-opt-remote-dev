FROM mcr.microsoft.com/devcontainers/anaconda:0-3

# Copy environment.yml (if found) to a temp location so we update the environment. Also
# copy "noop.txt" so the COPY instruction does not fail if no environment.yml exists.
# Make RUN commands use the new environment:
RUN conda create -n optenv python=3.9 -y
SHELL ["conda", "run", "-n", "optenv", "/bin/bash", "-c"]
RUN conda install -c conda-forge pyscipopt -y
COPY .devcontainer/requirements.txt requirements.txt
RUN pip install -r requirements.txt
