---
keywords: at.js プラグイン;サポートされるプラグイン;サポートされないプラグイン;ttMeta;ttmeta;mboxTrack
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.jsの最新バージョンに移行します。
title: at.jsのターゲットでサポートされていないレガシープラグインは何ですか。
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 82%

---


# at.js プラグイン

Adobe Target でのサポート対象およびサポート対象外の at.js プラグインについて説明します。

多くのユーザーが、カスタマイズしたプラグインおよび [!DNL mbox.js] の応答プラグインを構築しています。こうしたカスタムプラグインは、更新しないと [!DNL at.js] でサポートされない可能性があります。

ここに記載されていないプラグインを使用していて、状況を知りたい場合は、アカウント担当者にお問い合わせください。

多くの顧客が [!DNL at.js] で使用するプラグインの一部についての現在の状況は次の通りです。

| プラグイン | 詳細 |
|--- |--- |
| mboxTrack | 非対応。<br>これは [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 関数に置き換わります。新しい関数を適用するために、プラグインを更新します。<br>詳細については、「[統合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)」ページを参照してください。 |
| 永続的プロファイルバックアッププラグイン | 非対応。<br>このプラグインは、Target プロファイルの有効期間が 2 週間から 90 日に延長された際に廃止されました。mbox cookie の有効期限をチェックして、アカウントのプロファイル有効期間設定を確認します。<br>プロファイルの有効期間を 90 日に延長したい場合は、ClientCare にお問い合わせください。 |
| ttMeta | 古い SiteCatalyst プラグインは無効にして、[Adobe Target のレポートソースとして Adobe Analytics に置き換える](/help/c-integrating-target-with-mac/a4t/a4t.md)（A4T）必要があります。ttMeta プラグインは、無効にして [Adobe Experience Cloud デバッガー](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj)に置き換えてください。 |