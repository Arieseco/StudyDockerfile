# ベースイメージの指定
FROM python:3.9-slim

# metadata docker image inspectすると出てくる情報
LABEL maintainer="fwpc0811@gmail.com"
LABEL version="2.0"
LABEL description="simple python image02."

# 作業フォルダ
# 初期位置になるフォルダの作成
WORKDIR /tmp/mydir

# ファイルのコピー
# ローカルの現在のディレクトリにあるrequirements.txtをWORKDIRにコピーしている
COPY requirements.txt ${PWD}

#docker image build を行う際に実行するコマンド
# アプリケーションやモジュールのインストール、ユーザの追加などを行う
#pythonパッケージのインストール
RUN pip install -r requirements.txt

# 一時変数の定義 docker build時に指定する。
# docker image build --build-arg wdir=/tmp/src .
ARG wdir

# 作業ディレクトリを変更
WORKDIR $wdir
