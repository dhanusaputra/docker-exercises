FROM ubuntu
RUN apt-get update && apt-get install -y git curl
RUN git clone https://github.com/docker-hy/backend-example-docker.git
WORKDIR "/backend-example-docker"
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN npm install
RUN useradd -m appuser
RUN chown -R appuser /backend-example-docker
USER appuser
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD ["npm", "start"]

