# Zeabur に AgentBase をデプロイする

[Zeabur](https://zeabur.com) は、ワンクリックデプロイで AgentBase をデプロイできるサービスデプロイプラットフォームです。本ガイドは、Zeabur に AgentBase をデプロイする方法を説明します。

## 前提条件

開始する前に、以下の事項が必要です：

- Zeabur のアカウント。アカウントをお持ちでない場合は、[Zeabur](https://zeabur.com/) で無料のアカウントを登録できます。
- Zeabur のアカウントを開発者プラン（月額 5 ドル）にアップグレードする必要があります。詳細は [Zeabur 定价](https://zeabur.com/pricing) をご覧ください。

## AgentBase を Zeabur にデプロイする

Zeabur チームはワンクリックデプロイテンプレートを用意しています。以下のボタンをクリックするだけで開始できます：

[![Deploy to Zeabur](https://zeabur.com/button.svg)](https://zeabur.com/1D4DOW)

ボタンをクリックすると、Zeabur 上のテンプレートページに移動し、デプロイの詳細情報と説明を確認できます。

<figure><img src="../../.gitbook/assets/zeabur-template-overview.jpeg" alt="Zeabur テンプレート概要"><figcaption></figcaption></figure>

デプロイボタンをクリックした後、生成されたドメイン名を入力し、そのドメイン名を AgentBase インスタンスにバインドし、他のサービスに環境変数として注入します。
次に、お好みのリージョンを選択し、デプロイボタンをクリックすると、数分以内に AgentBase インスタンスがデプロイされます。

<figure><img src="../../.gitbook/assets/zeabur-region-select.png" alt="リージョンを選択"><figcaption></figcaption></figure>

デプロイが完了すると、Zeabur コンソール上にプロジェクトページが表示されます。以下の図のように、デプロイ中に入力したドメイン名が自動的に NGINX サービスにバインドされ、そのドメイン名を使用して AgentBase インスタンスにアクセスできます。

<figure><img src="../../.gitbook/assets/zeabur-project.png" alt="Zeabur プロジェクト概要"><figcaption></figcaption></figure>

また、NGINX サービスページのネットワーキングタブでドメイン名を変更することもできます。詳細については [Zeabur ドキュメント](https://zeabur.com/docs/deploy/domain-binding) を参照してください。