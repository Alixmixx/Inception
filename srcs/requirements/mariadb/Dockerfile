FROM debian:buster

# Install packages
RUN apt-get update -y && apt-get install mariadb-server -y

# Copy files
COPY ./tools/50-server.cnf /etc/mysql/mariadb.conf.d/

COPY ./tools/start.sh /
# Set permissions
RUN chmod +x /start.sh

# Expose ports
EXPOSE 3306

# Start server
CMD ["/start.sh"]

# Build command
# docker build -t mariadb srcs/requirements/mariadb

# Run command
# docker run -it --rm --name mariadb -p 3306:3306 mariadb
