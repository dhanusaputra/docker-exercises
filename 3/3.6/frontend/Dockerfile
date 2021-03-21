FROM node:alpine as build-stage
RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/frontend-example-docker.git
WORKDIR "/frontend-example-docker"
RUN npm install && \
    npm run build && \
    apk del git

FROM alpine
COPY --from=build-stage /frontend-example-docker/dist /dist
RUN apk add --no-cache npm && \
    npm install -g serve && \
    adduser -D appuser && \
    chown -R appuser /dist
USER appuser
EXPOSE 5000
ENV API_URL=http://localhost:8000
CMD serve -s -l 5000 dist 

