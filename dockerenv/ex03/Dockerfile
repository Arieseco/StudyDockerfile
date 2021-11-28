FROM ubuntu:20.04

# install Nginx
# && でつなげて1回の命令で済まそうとしている（高速化が目的）
# rm -rf パッケージ管理システムのキャッシュをクリア（サイズ縮小）
# ビルド時間が短く、サイズが小さいものが良しとされるため。
RUN apt-get update && apt-get install -y \
    nginx \
    tzdata \
&& rm -rf /var/lib/apt/lists/*

# timezone
# コンテナの中でも使用できる変数 docker buildで指定することはできない
ENV TZ=Asia/Tokyo

# ポートの指定
# コンテナのアプリケーションで使用するポート番号を指定
# -pオプションで割り当てる
# docker run -d -p 8080:80 nginx
EXPOSE 80

# ファイルのコピー
COPY src/index.html /var/www/html/

# Nginxの起動
# CMD docker run の際に実行するコマンド
# CMD は１つしか書けない
# nginx -g daemon off;
# -g グローバル設定 バックグラウンドで実行するとコンテナがすぐに停止してしまうため
CMD ["nginx", "-g", "daemon off;"]

# Release file for xxxx is not valid yet対策
# sudo hwclock -s コマンドのちDocker buildする
