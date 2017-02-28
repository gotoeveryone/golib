# Golang用共通ライブラリ

## 概要

Golangの共通ライブラリとして処理をまとめてあります。
現在は以下のようなことができます。

1. 設定ファイルをJSONより読み込み
2. ログ出力をレベル分け
3. メール通知

## 前提

以下がインストールされていること

- Golang

## 実行準備

任意ディレクトリに以下のような内容で「config.json」を作成してください。  
※値は実際に利用するサービスの接続情報を設定すること。  

```json
{
    "log": {
        "path": "",
        "level": "INFO",
    },
    "redis": {
        "host": "",
        "port": 0,
        "auth": ""
    },
    "db": {
        "name": "",
        "host": "",
        "port": 0,
        "user": "",
        "password": ""
    },
    "mail": {
        "smtp": "",
        "port": 0,
        "user": "",
        "password": "",
        "to": [""]
    }
}
```

以下コマンドで実行時、設定ファイルの格納ディレクトリを示す`--conf`オプションで対象ディレクトリを指定してください。  
未指定の場合は実行ディレクトリを参照します。  

```sh
go run <my_program> --conf=/path/to/
```