# test-go-api

* aws lambda(golang)で動かすサンプルコード

## 準備

Windows環境でlambdaにアップロードするzipは専用ツールを使用する必要がある。  
以下のコマンドでインストールする。

```
go.exe get -u github.com/aws/aws-lambda-go/cmd/build-lambda-zip
```

## ライブラリのインストール

```
go get github.com/aws/aws-lambda-go/lambda
```

## ビルド

```
set GOOS=linux
set GOARCH=amd64

go build -o test-go-api test-go-api.go
%USERPROFILE%\Go\bin\build-lambda-zip.exe -o test-go-api.zip test-go-api
```

zipファイルが生成されるのでawsマネジメントコンソールのlambdaの画面からアップロードする。
