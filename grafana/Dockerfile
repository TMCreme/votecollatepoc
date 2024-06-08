# Use the official Grafana base image
FROM grafana/grafana:10.2.1

# Set the working directory
WORKDIR /usr/share/grafana

# Copy custom provisioning configuration
# COPY ./provisioning /etc/grafana/provisioning

# Copy custom dashboards
# COPY ./dashboards /var/lib/grafana/dashboards

# Environment variables to configure Grafana
ENV GF_SECURITY_ADMIN_USER=admin
ENV GF_SECURITY_ADMIN_PASSWORD=admin
# ENV GF_USERS_ALLOW_SIGN_UP=false

# ENV GF_LOG_LEVEL=debug
ENV GF_INSTALL_PLUGINS=grafana-clock-panel,grafana-simple-json-datasource

ENV GF_DATABASE_TYPE=postgres
ENV GF_DATABASE_HOST=${POSTGRES_HOST}:${POSTGRES_PORT}
ENV GF_DATABASE_NAME=postgres
ENV GF_DATABASE_USER=postgres
ENV GF_DATABASE_PASSWORD=${POSTGRES_PASSWORD}

# Expose Grafana default port
EXPOSE 3000

VOLUME /var/lib/grafana

# Run the entrypoint from the base image
ENTRYPOINT ["/run.sh"]
