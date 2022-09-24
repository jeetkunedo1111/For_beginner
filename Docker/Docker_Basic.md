Docker の誕生
Docker は Container 基盤のオープンソース仮想化プラットファムである。実行環境をコンテナというものを活用し、抽象化し、同一のインタフェースを提供するため、プログラムの Deploy および管理は単純化して売れる。実際に Docker 開発以前はエンジニアは開発の際にコードを修正した際に、自分の PC ではうまく実行されるが他の PCではエラーが発生することをよく経験してきたはずである。このようなインフラの可変性に対する問題は常に存在していると考えられる。このような問題は Docker が登場してからか行けるされたといえるだろう。

VM vs CONTAINER

VM -> Infrastructure -> hypervisor ->
   -> Bins/Libs -> APP1

CONTAINER -> Infrastructure -> Operating System -> Docker Engin -> Bins/Libs -> APP1
