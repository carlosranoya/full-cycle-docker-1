FROM golang:latest as builder

WORKDIR /usr/temp

COPY codeeducation.go /usr/temp

RUN go build codeeducation.go

FROM scratch
COPY --from=builder /usr/temp/codeeducation code_education
CMD ["./code_education"]
