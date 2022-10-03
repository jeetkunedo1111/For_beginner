## Dockerfile

Docker file| 基本命令  
---------|-----------
FROM Base Image| 指定  
RUN |命令実行  
CMD:Container |命令実行  
LABEL|LABEL 設定  
EXPOSE |PORT EXPORT
ENV|環境変数
ADD |Add file/Directory  
COPY |Copy file  
ENTRYPOINT |CONTAINER 実行命令  
VOLUME |VOLUME MOUNT  
USER |User 指定  
WORKDIR |作業ディレクトリ  
ARG |Dodckerfile 中の変数  
ONBUILD | BUILD 完了後実行される命令  
STOPSIGNAL |System call signal 設定  
HEALTHCHECK |CONTAINER HEATLTH CHECK  
SHELL |基本SHELL 設定  
-------------------------------------

## Dockerfile 作成

Dodkcerfile にはDocker Contianer をどんな Docker Image から生成するのかという情報を技術しなけばならない。
この Image をベースイメージという

FROM 命令
ベースイメージ情報記述

FROM[IMAGE_NAME]
FROM[IMAGE_NAME]:[TAG_NAME]
FROM[IMAGE_NAME]:[DIGEST]

- Dockerfile の build と IMAGE_LAYER
  - Docker build 命令書式
  ```
  docker build -t [生成数Rイメージ]：[Tag_name][Dockerfile の場所]
  ```
  - Docker build 実行例
  Dockerfile から sample というイメージを作成 TAG_NAME: 1.0
  Dockerfile の保存場所を絶対経路として指定 /home/docker/sample 相対経路として指定も可能
   ```
   docker build -t sample:1.0 /home/docker/sample
   ```
- Image 確認
 docker image ls

- 新しいイメージ作成の例
 ```
 docker build -t sample:2.0 /home/docker/sample
 ```
- ファイル名を指定した docker build 命令を実行
 ```
 docker build -t sample -f Dockerfile.base .
 ```
- 標準入力での build
 標準入力を経由し Dockerfile をしてして build することも可能
 標準入力の内容としては Dodkcerfile の内容を Docker build 命令を引数として渡すため、-(ハイフン)を指定する
 ```
 docker build - < Dockerfile
 ```
- Docker Image の Layer 構造
  - 4つの命令を持っている Dockerfile の例
  Dockerfileと同じ Directory に任意の'index.html'という名前のファイルを生成し Docker build image を作成すると、各レイアごとにイメージが生成され4つのイメージが生成される
  # STEP:1 Ubuntu (base image)
  FROM ubuntu:latest

  # STEP:2 Nginx install
  RUN apt-get update && apt-get install -y -q nginx

  # STEP:3 file copy
  COPY index.html /usr/share/nginx/html

  # STEP4: Nginx Start
  CMD ["nginx", "-g", "daemon off;"]




