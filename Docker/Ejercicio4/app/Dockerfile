# Se usa la imagen de python en docker
FROM python:3.9-slim

# Crear un directorio de trabajo
WORKDIR /app

# Se copia el archivo de requirements que tiene que librerias son necesarias para el programa.
COPY requirements.txt ./

# Se ejecuta la linea de comando para instalar las librerias necesarias.
RUN pip install --no-cache-dir -r requirements.txt

# Se copian todos los archivos en la aplicacion a crear

COPY . .

# Se expone un puerto para poder crear el contenedor
EXPOSE 5000

# Ejecutar la aplicacion
CMD ["python", "app.py"]