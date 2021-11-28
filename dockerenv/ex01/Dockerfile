# ベースイメージの指定
#PCにイメージが取得済であればそれを使用する
#PCにイメージがない場合、DockerHubから取得する。
FROM python:3.9-slim

# metadata docker image inspectすると出てくる情報
# inspect情報を保持するコマンド
# docker inspect ex01/python:1.0 > inspect.txt
LABEL maintainer="fwpc0811@gmail.com"
LABEL version="1.0"
LABEL description="simple python image."

# 作業フォルダ
# 初期位置になるフォルダの作成
WORKDIR /tmp/mydir
