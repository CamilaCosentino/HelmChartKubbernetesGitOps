# ---- Etapa 1 - Construcción la aplicación base----
FROM python:3.9.18-alpine3.18 as build
WORKDIR /app
COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt
COPY . .
EXPOSE 3000
CMD ["python", "main.py"]



