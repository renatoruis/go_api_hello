FROM golang:alpine
WORKDIR /go
#RUN go get -d -v .
COPY main.go .
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix cgo -o main .

FROM alpine:latest  
WORKDIR /app/
COPY --from=0 /go/main .
CMD ["./main"]  