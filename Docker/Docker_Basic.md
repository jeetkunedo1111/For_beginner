Docker の誕生
Docker は Container 基盤のオープンソース仮想化プラットファムである。実行環境をコンテナというものを活用し、抽象化し、同一のインタフェースを提供するため、プログラムの Deploy および管理は単純化して売れる。実際に Docker 開発以前はエンジニアは開発の際にコードを修正した際に、自分の PC ではうまく実行されるが他の PCではエラーが発生することをよく経験してきたはずである。このようなインフラの可変性に対する問題は常に存在していると考えられる。このような問題は Docker が登場してからか行けるされたといえるだろう。

VM vs CONTAINER

VM -> Infrastructure -> hypervisor ->
   -> Bins/Libs -> APP1

CONTAINER -> Infrastructure -> Operating System -> Docker Engin -> Bins/Libs -> APP1

Dockerfile build -> DockerImage -> push -> Repository

必要な時に Pull をして使うだけ。

docker の概念を簡単に
- Image

 Image はプログラムだと考えると望ましい。image layer が集合体として、Image を作ることも可能。Read-only で Immutable

- Container

 Container はProcess だと思うと望ましい。Write 可能で揮発性でメモリに常駐する。
- Dockerfile

 Instruction set で docker image を作る説明書だと考えればよい

- Registry

 Github のような Image ストレージであり、代表的な Public registry として、DockerHub がある。

