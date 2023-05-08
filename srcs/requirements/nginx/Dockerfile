FROM debian:buster

# Install packages
RUN apt update -y && apt install nginx -y && apt install openssl -y

RUN openssl req -x509 -nodes -days 365 -newkey rsa:2048 \
	-subj "/C=FR/L=PARIS/O=MIAO/OU=student/CN=[amuller.miao.fr](http://amuller.42.fr/)" \
	-keyout /etc/ssl/private/nginx-selfsigned.key \
	-out /etc/ssl/certs/nginx-selfsigned.crt

# Copy files
COPY ./tools/start.sh /

# Set permissions
RUN chmod +x /start.sh

# Expose ports
EXPOSE 443

# Start server
CMD ["/start.sh"]

# Build command
# docker build -t nginx srcs/requirements/nginx

# Run command
# docker run -it --rm --name nginx -p 443:443 nginx
