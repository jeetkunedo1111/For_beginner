## Openstack の基礎
- Openstack とは？

  -  Pulling された仮想リソースを使い、Private および Public Cloud を構築し、管理する Opensource Platform

  - Openstack Platform を含む、ツール "Project"はComputing,Networking,Storage,Identity およびイメージサービスの軸であるCloud Computing Service を処理する。

  - 数十個以上のオプションを Bundel を結び Deploy 可能な固有の Cloud を生成することができる

  - 仮想化には多様な Vendor ごとのプログラムで Storage,CPU,RAM と同じリソースを抽象化し Hypervisor を通じて分割した圧、必要によって Deploy をする

  - OpenStack は一貫した、アプリケーションプログラミングインタフェースのセットを使い、外套の仮想リソースを分離された Pull で一層抽象化し、それに基づいた標準クラウドコンピューティングツールにて管理者とユーザが直接にインタレクションすることができる。

 - Openstack は単純な仮想管理 Platform なのか？

    - 似ているところも多いが同一ではない
    - Openstack と仮想化管理 Platform すべて仮想リソースを基に
    し、Vendor 毎の環境でプロセスの検索、レポートを自動化できる
    - 仮想化管理 PlatForm ではリソースの操作が簡単な一方、Openstack ではツールの組み合わせを実行するため、実際に仮想リソースを使う違いがある。
    - このようなツールは NIST が提示したクラウドコンピューティングの５つの基準である、ネットワーク、Pulling されたリソース、ユーザインタフェース、プロビジョニング機能。自動リソースっ制御/割り当てを満たすクラウド環境を構築できるようにする

 - OpenStack 作動方法
    - OpenStack は基本的にスクリプトと呼ばれる一連の命令語である。
    - このようなスクリプトは Project と呼ばれるパッケージで構成され、クラウド環境を構築するタスクを与える
    - Openstack はこのような環境を構築するために2つの類型のソフトウェアを構築する
    - Openstack はその事態でリソースを仮想化するものではなく、リソースを用いてクラウドを構築する
    - Openstack はまた、命令を実行するよりは基本ＯＳで命令を与える
    - Openstack,仮想化および基本 OSの三つの技術すべてが連動されなければならない
    - そのような相互依存性のためOpenstack クラウドは Linux を使い Deploy を行う
 - Openstack の構成要素
    - Openstack のアーキテクチャは多くのオープンソースプロジェクトで構成されている
    - Undercloud はシステム管理者が最終ユーザの Openstack 環境、すなわち Overcloud を設定し、管理者は必要なコーア構成要素で成り立っている。
    - この6つの核心あサービスは残りのプロジェクトで Dashboard,            Ochestration,Bare-Metal Provisioning, Messaging, Container,  Governance を処理できるインフラになる

 - Openstack のサービス構成
   - Nova-Compute Project
     - Nova は Hypervisor を管理するAPI提供
     - Instance(VM)生成管理
     - 制御機能がControl Nodeに位置し、compute node 管理
   - Stroage(Swift,Cinder)Projects
     - Cloud Storage サービス： ストレー所およびストレージAPI
     提供
     - Block Storage(ハードディスク): Cinder, 定型性保存適合(固定フィルード、エクセル)-> 問題の際に、フォーマットできないため新しく生成
     - Object Storage: Swift, 非定型性保存適合(イメージ),ユーザアカウント別 Storage 空間を提供可能
     - 共有 Storage: Manila, NFS & CIF5 共有ファイルサービス
  - Ceph - Openstack 下のプロジェクトではない
     - Ceph のRDB,RADIOS：分散 Storage のためにほかの Opensource サービスですべての種類の Storage 関連サービス提供するプロジェクト
  - Glance(CD-ROM と似たような機能)
      - Openstack でOS のイメージを管理
      - 多様な Hypervior で使える VM IMAGE を管理し、VM にインストールされたOSの保管および管理
  - glance-api でイメージを登録、削除および管理
  - glance-api を使い、glance-registry,glancedatabase にイメージを管理
  - Image の登録際に、Glance-registryを通じて、glance-database に登録
  - 登録されたイメージを使い、Glance-database にすぐに使用を Request する
  - Keystone
    - 物理サーバ内の Compute,image,network,storageのようなResourceに関する認証管理
    - ユーザ認証を通じて物理サーバ内の資源を使えるように管理
  - Horizon
    - Openstack Dashboard Service
    - Horizon はユーザが Web Service を使用し、Dashboard はpython Django Framewor で表す
  - Neutron
    - Network サービスである Neutron はFolsomバージョンではQuantumという名前でオープン
    - そのあと、Grizzly バージョンで Hanana バージョンにて Neutron に変更
    - 既存の Openstack の Network サービスは Nova-newwork が担っていたが、SDN の概念が入り別の Network Project に分離
    - Neutron は Neutron サーバ、Agent, Plugin, MessageQue, NetworkProvider, Database で構成される
    - Netron は多様なネットワーク Plugin と Network Model を支援
    