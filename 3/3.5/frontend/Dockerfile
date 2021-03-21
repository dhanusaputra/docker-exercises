FROM node:alpine
RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git
WORKDIR "/frontend-example-docker"
RUN npm install && \
    apk del git && \
    adduser -D appuser && \
    chown -R appuser /frontend-example-docker
USER appuser
EXPOSE 5000
ENV API_URL=http://localhost:8000
CMD ["npm", "start"]

