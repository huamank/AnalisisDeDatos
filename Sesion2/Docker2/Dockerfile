FROM python:3.9-slim

# Crear el directorio de trabajo
WORKDIR /app

# Copiar el archivo requirements.txt
COPY requirements.txt ./

# Instalar dependencias
RUN pip install --no-cache-dir -r requirements.txt

# Copia todos los archivos de la carpeta acrual al workdir
COPY . .

# Exponer el puerto
EXPOSE 5000

# Comando para ejcutar
CMD ["python", "app.py"]