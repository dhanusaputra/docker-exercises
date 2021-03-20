FROM ubuntu
RUN apt-get update && apt-get install -y git curl
RUN git clone https://github.com/docker-hy/frontend-example-docker.git
WORKDIR "/frontend-example-docker"
RUN curl -sL https://deb.nodesource.com/setup_10.x | bash
RUN apt install -y nodejs
RUN npm install
EXPOSE 5000
ENV API_URL=http://localhost:80
CMD ["npm", "start"]

