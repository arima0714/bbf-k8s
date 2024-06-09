FROM golang:1.21 AS builder
WORKDIR /app
COPY . .
ENV CGO_ENABLED=0
RUN go build -o hello .

# Docker が公式で用意している最小のイメージ
FROM scratch 
# -from=<ステージ名> で指定されたステージの成果物をこのステージにコピー
COPY --from=builder /app/hello /hello
ENTRYPOINT ["/hello"]
