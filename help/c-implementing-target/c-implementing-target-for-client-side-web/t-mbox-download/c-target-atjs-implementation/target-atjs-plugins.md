---
description: Targetのサポート対象とサポートされていないat. jsプラグインに関する情報です。
keywords: at. jsプラグイン;サポートされているプラグイン;サポートされていないプラグイン;ttMeta;ttmeta;mboxTrack
seo-description: Adobe Targetのサポート対象とサポートされていないat. jsプラグインに関する情報です。
seo-title: Adobe Target用at. jsプラグイン
solution: 'Target '
title: at.js プラグイン
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: c3afa420f33f98d7c4bb332acdef7a248fe4670a

---


# at.js plug-ins{#at-js-plug-ins}

Adobe Targetのサポート対象とサポートされていないat. jsプラグインに関する情報です。

多くのユーザーが、カスタマイズしたプラグインおよび [!DNL mbox.js] の応答プラグインを構築しています。こうしたカスタムプラグインは、更新しないと [!DNL at.js] でサポートされない可能性があります。

ここに記載されていないプラグインを使用していて、状況を知りたい場合は、アカウント担当者にお問い合わせください。

多くの顧客が [!DNL at.js] で使用するプラグインの一部についての現在の状況は次の通りです。

| プラグイン | 詳細 |
|--- |--- |
| mboxTrack | 非対応。<br>これは [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 関数に置き換わります。新しい関数を適用するために、プラグインを更新します。<br>詳細については、「[統合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)」ページを参照してください。 |
| 永続的プロファイルバックアッププラグイン | 非対応。<br>このプラグインは、Target プロファイルの有効期間が 2 週間から 90 日に延長された際に廃止されました。mbox cookie の有効期限をチェックして、アカウントのプロファイル有効期間設定を確認します。<br>プロファイルの有効期間を 90 日に延長したい場合は、ClientCare にお問い合わせください。 |
| ttMeta | Old SiteCatalyst plugins should be disabled and replaced with [Adobe Analytics as the reporting source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). ttMeta プラグインは、無効にして [Adobe Experience Cloud デバッガー](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj)に置き換えてください。 |