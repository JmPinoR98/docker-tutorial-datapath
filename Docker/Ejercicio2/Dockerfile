# Imagen de sistema operativo para el servidor que permitira la instalacion de Python y Jupyter Notebook
FROM ubuntu:20.04

# Se configua el sistema operativo para que no tenga la forma grafica
ENV DEBIAN_FRONTEND=noninteractive

# Actualizar el sistema operativo
RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-dev \
    build-essential \
    wget \
    && apt-get clean

RUN pip3 install --upgrade pip && \
    pip3 install Notebook

# Crear la libreria en que se va a trabajar
WORKDIR /workspace

# Crear directorio de configuracion de Jupyter
RUN mkdir -p /root/.jupyter

# Añadir el archivo de configuración de Jupyter 
RUN echo "c.NotebookApp.token = ''" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.password = ''" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.open_browser = False" >> /root/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.allow_root = True" >> /root/.jupyter/jupyter_notebook_config.py

# Exponer el puerto de conexion del contenedor
EXPOSE 8888

# Ejecucion del contenedor
CMD ["jupyter","notebook","--ip=0.0.0.0","--no-browser","--allow-root"]

