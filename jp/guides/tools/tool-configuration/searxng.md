# SearXNG

> ツール作者 @Junytang。
SearXNGは、様々な検索サービスの結果を統合する無料のインターネットメタサーチエンジンです。 AgentBaseはSearXNGにアクセスするためのインターフェイスを実装しており、AgentBaseから直接利用することができます。 以下では、Dockerを使用してSearXNGをAgentBaseに統合する手順を説明します。他の方法でSearXNGをインストールしたい場合は、[こちら](https://docs.searxng.org/admin/installation.html)を参照してください。

## 1. Dockerを使用してSearXNGコンテナをインストールする
設定ファイルは `agentbase/api/core/tools/provider/builtin/searxng/docker/settings.yml` にあり、[こちら](https://docs.searxng.org/admin/installation.html)を参照してください。

## 2. AgentBaseのルートディレクトリでDockerコンテナを起動する
```
cd agentbase
docker run --rm -d -p 8081:8080 -v "${PWD}/api/core/tools/provider/builtin/searxng/docker:/etc/searxng" searxng/searxng
```

## 3. AgentBaseにSearXNGを統合する
`ツール > SearXNG > 認証へ行く` でアクセスアドレスを入力します。Dockerを使用してAgentBaseを展開する場合、アドレスは一般的に`http://host.docker.internal:8081`となります。