FROM node:alpine
RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/backend-example-docker.git
WORKDIR "/backend-example-docker"
RUN npm install && \
    apk del git && \
    adduser -D appuser && \
    chown -R appuser /backend-example-docker
USER appuser
EXPOSE 8000
ENV FRONT_URL=http://localhost:5000
CMD ["npm", "start"]

