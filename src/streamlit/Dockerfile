# Set the base image
FROM python:3.11-alpine

# Define o diretório de trabalho
WORKDIR /app

# Instala dependências do sistema necessárias
RUN apk add --no-cache \
    build-base \
    libffi-dev \
    gcc \
    musl-dev \
    libc-dev \
    python3-dev \
    py3-pip \
    jpeg-dev \
    zlib-dev \
    freetype-dev \
    lcms2-dev \
    openjpeg-dev \
    tiff-dev \
    tk-dev \
    tcl-dev \
    libxml2-dev \
    libxslt-dev \
    libjpeg-turbo-dev \
    libpng-dev \
    libwebp-dev \
    && pip install --upgrade pip

# Copia apenas os arquivos essenciais
COPY app/ .

# Instala as dependências do Python
RUN pip install --no-cache-dir -r requirements.txt

# Default port
EXPOSE 8501

# Start Streamlit
CMD ["streamlit", "run", "app.py", "--server.address=0.0.0.0", "--server.runOnSave=true"]