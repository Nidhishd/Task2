FROM nginx:1.14.2

# Creating Dir for nginx DocumentRoot
RUN mkdir -p /var/www/html

# Copying json file to serve as an index for Nginx
COPY static.json /var/www/html/index.html

# Copying updated nginx configuration file and make as a default.
COPY nginx-conf/nginx.conf /etc/nginx/conf.d/default.conf