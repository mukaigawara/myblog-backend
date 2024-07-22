FROM golang:1.23-rc-alpine3.19

# このコメント以後のコメントは[/go/src/app/]フォルダーにて実行させるように指定します
WORKDIR /go/src/app/
# ホストPCの[./api]フォルダーの配置されたソースコードを[/go/src/app/]フォルダーにコピーします
COPY ./api .

# OSのインストール済みのパッケージをバージョンアップし、必要なパッケージをインストールします
RUN apk upgrade --update && \
    apk --no-cache add git gcc musl-dev
    # TODO: AIRの設定を行う

# ホットリロード用のツール
RUN go install github.com/air-verse/air@latest
# airツールを起動します
CMD ["air", "-c", ".air.toml"]