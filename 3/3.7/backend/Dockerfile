FROM golang:alpine as build-stage
RUN apk add --no-cache git && \
    git clone https://github.com/docker-hy/material-applications.git && \
    cd material-applications/example-backend && \
    go build .

FROM golang:alpine
COPY --from=build-stage /go/material-applications/example-backend/server server
ENV REQUEST_ORIGIN=http://localhost:5000
ENV PORT=8000
EXPOSE 8000
CMD ./server
