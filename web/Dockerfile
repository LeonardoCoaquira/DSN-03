# Utilizar una imagen ligera de Nginx como base
FROM nginx:alpine

# Copiar los archivos de la aplicación al directorio de trabajo de Nginx
COPY . /usr/share/nginx/html

# Exponer el puerto en el que la aplicación se ejecutará (por defecto, Nginx usa el puerto 80)
EXPOSE 80

# Comando para iniciar Nginx en primer plano
CMD ["nginx", "-g", "daemon off;"]
