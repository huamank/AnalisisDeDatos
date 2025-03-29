# Utiliza ubuntu 20.04
FROM ubuntu:20.04

ENV DEBIAN_FRONTED=noninteractive

# Actualiza e Installa dependencias
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    build-essential \
    wget \
    && apt-get clean

# Instalamos Jupyter
RUN pip3 install --upgrade pip && \
    pip3 install notebook

# Crear directorio de trabajo
WORKDIR /workspace

# Crear el directorio de Jupyter
RUN mkdir -p /root/.jupyter

# Agregar configuraciones de Jupyter

RUN echo "c.NotebookApp.token = '' " >> /root/.jupyter/jupyter_notebook_config.py && \
echo "c.NotebookApp.password = ''" >> /root/.jupyter/jupyter_notebook_config.py && \
echo "c.NotebookApp.open_browser = False" >> /root/.jupyter/jupyter_notebook_config.py && \
echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py

# Expone el puerto 8888 para jupyter notebook
EXPOSE 8888

# Comando para inicializar jupyter notebook
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root"]