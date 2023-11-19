# Utilizar la imagen oficial de Node.js LTS
FROM node:14 as build

# Establecer el directorio de trabajo
WORKDIR /app

# Copiar los archivos de la aplicación (package.json y package-lock.json) para aprovechar la caché de capas de Docker
COPY package*.json ./

# Instalar dependencias
RUN npm install

# Copiar el resto de la aplicación
COPY . .

# Construir la aplicación React
RUN npm run build

# Etapa de producción
FROM nginx:alpine

# Copiar los archivos construidos de la etapa de construcción a la carpeta de Nginx
COPY --from=build /app/build /usr/share/nginx/html

# Exponer el puerto 80 (puerto predeterminado de Nginx)
EXPOSE 80

# Comando para iniciar el servidor Nginx
CMD ["nginx", "-g", "daemon off;"]