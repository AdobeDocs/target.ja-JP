---
description: サポート対象およびサポート対象外の at.js プラグインに関する情報を紹介します。
keywords: at.jsプラグイン;サポートされているプラグイン;サポートされていないプラグイン
seo-description: サポート対象およびサポート対象外の at.js プラグインに関する情報を紹介します。
seo-title: at.js プラグイン
solution: 'Target '
title: at.js プラグイン
topic: Standard
uuid: ef36b2b2-bf6d-497e-b3f5-2b572a1b8a8d
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# at.js プラグイン{#at-js-plug-ins}

サポート対象およびサポート対象外の at.js プラグインに関する情報を紹介します。

多くのユーザーが、カスタマイズしたプラグインおよび [!DNL mbox.js] の応答プラグインを構築しています。こうしたカスタムプラグインは、更新しないと [!DNL at.js] でサポートされない可能性があります。

ここに記載されていないプラグインを使用していて、状況を知りたい場合は、アカウント担当者にお問い合わせください。

多くの顧客が [!DNL at.js] で使用するプラグインの一部についての現在の状況は次の通りです。

| プラグイン | 詳細 |
|--- |--- |
| mboxTrack | 非対応。<br>これは [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) 関数に置き換わります。新しい関数を適用するために、プラグインを更新します。<br>詳細については、「[統合](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/target-atjs-integrations.md)」ページを参照してください。 |
| 永続的プロファイルバックアッププラグイン | 非対応。<br>このプラグインは、Target プロファイルの有効期間が 2 週間から 90 日に延長された際に廃止されました。mbox cookie の有効期限をチェックして、アカウントのプロファイル有効期間設定を確認します。<br>プロファイルの有効期間を 90 日に延長したい場合は、ClientCare にお問い合わせください。 |
| ttMeta | 対応.<br>このプラグインは、at.js で引き続き使用できます。 |