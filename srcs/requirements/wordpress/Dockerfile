FROM debian:buster

# Install packages
RUN apt update -y

RUN apt install php-fpm php-mysql -y

RUN apt install curl -y

# Copy files
COPY ./tools/start.sh /
COPY ./tools/wp-config.php /

# Set permissions
RUN chmod +x /start.sh

# Start server
CMD ["/start.sh"]

# Build command
# docker build -t wordpress srcs/requirements/wordpress

# Run command
# docker run -it --rm --name wordpress -p 443:443 wordpress
