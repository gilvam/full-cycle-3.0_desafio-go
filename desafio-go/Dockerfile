FROM golang:latest as build-stage
WORKDIR /src
COPY main.go .
RUN go build main.go


FROM scratch  as production-stage
WORKDIR /root/
COPY --from=build-stage /src/main .
CMD [ "./main" ]
