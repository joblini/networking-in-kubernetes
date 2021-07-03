FROM golang:latest AS build
WORKDIR /
COPY demoapp.go /demoapp.go
RUN go mod init demoapp
RUN go get github.com/go-sql-driver/mysql
RUN go get github.com/go-errors/errors
RUN go build /demoapp.go

FROM nicolaka/netshoot
COPY --from=build /demoapp /demoapp
EXPOSE 9000
CMD "/demoapp"