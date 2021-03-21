FROM ubuntu
RUN apt-get update && apt-get install -y git curl ca-certificates && \
    git clone https://github.com/docker-hy/backend-example-docker.git
WORKDIR "/backend-example-docker"
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt install -y nodejs && \
    npm install && \
    apt-get purge -y --auto-remove git curl && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -m appuser && \
    chown -R appuser /backend-example-docker
USER appuser
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD ["npm", "start"]

