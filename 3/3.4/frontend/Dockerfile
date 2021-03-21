FROM ubuntu
RUN apt-get update && apt-get install -y git curl ca-certificates && \
    git clone https://github.com/docker-hy/frontend-example-docker.git
WORKDIR "/frontend-example-docker"
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash && \
    apt install -y nodejs && \
    npm install && \
    apt-get purge -y --auto-remove curl git && \
    rm -rf /var/lib/apt/lists/* && \
    useradd -m appuser && \
    chown -R appuser /frontend-example-docker
USER appuser
EXPOSE 5000
ENV API_URL=http://localhost:8000
CMD ["npm", "start"]

