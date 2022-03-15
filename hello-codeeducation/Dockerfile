FROM golang:1.17.7-alpine as base

WORKDIR /src

RUN go mod init desafio

COPY *.go ./

RUN CGO_ENABLED=0

RUN go build -o /hello-codeeducation

# stage 2
FROM scratch

WORKDIR /

COPY --from=base /hello-codeeducation /

CMD [ "/hello-codeeducation" ]