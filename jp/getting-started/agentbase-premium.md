---
description: プレミアムPremium
---

# AgentBase Premium

AgentBase Premiumは[AWS AMI](https://docs.aws.amazon.com/ja_jp/AWSEC2/latest/UserGuide/ec2-instances-and-amis.html)製品であります。これにより、ブランドのカスタマイズが可能で、AWS EC2にワンクリックで展開できます。[AWS Marketplace](https://aws.amazon.com/marketplace/pp/prodview-t22mebxzwjhu6)から購読し、次のようなシナリオに最適です：

* 中小企業が1つ以上のアプリケーションをサーバーに構築し、データのプライバシーに関心がある場合。
* [AgentBase Cloud](https://docs.agentbase.ai/v/ja-jp/getting-started/cloud)のサブスクリプションプランに関心があり、しかし、ユースケースが[プラン](https://agentbase.ai/pricing)で提供されるリソースを超える場合。
* AgentBase Enterpriseを組織内で導入する前に、POC検証を行いたい場合。

### セットアップ

AgentBaseを初めて使用する際には、管理者初期化パスワード（EC2インスタンスIDとして設定）を入力し、セットアッププロセスを開始してください。

AMIを展開した後は、EC2コンソールで見つかるインスタンスのパブリックIPを使用してAgentBaseにアクセスします（デフォルトではHTTPポート80を使用します）。

### アップグレード

EC2インスタンスで、次のコマンドを実行してください：

```
git clone https://github.com/agent-base/agentbase.git /tmp/agentbase
mv -f /tmp/agentbase/docker/* /agentbase/
rm -rf /tmp/agentbase
docker-compose down
docker-compose pull
docker-compose -f docker-compose.yaml -f docker-compose.override.yaml up -d
```

### カスタマイズ

セルフホスト展開の場合と同様に、EC2インスタンス内の.envファイルの環境変数を必要に応じて変更することができます。その後、以下のコマンドを使用してAgentBaseを再起動してください：

```
docker-compose down
ocker-compose -f docker-compose.yaml -f docker-compose.override.yaml up -d
```
