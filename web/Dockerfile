# Use a Node 16 base image
FROM node:16-alpine

# Establecer el directorio de trabajo en /app
WORKDIR /app

# Copiar los archivos de configuración
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar la aplicación
COPY . .

# Construir la aplicación para producción
RUN npm run build

# Exponer el puerto en el que la aplicación se ejecutará
EXPOSE 80

# Comando para ejecutar la aplicación
CMD ["npx", "serve", "-s", "build"]
