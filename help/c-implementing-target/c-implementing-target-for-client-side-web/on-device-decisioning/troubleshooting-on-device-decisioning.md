---
keywords: 実装；javascriptライブラリ；js;atjs;on-device decisioning;on device decisioning;at.js;on-device;on device；トラブルシューティング；トラブルシューティング
description: at.jsライブラリを使用したオンデバイス判定のトラブルシューティング方法について説明します。
title: at.js JavaScriptライブラリを使用したデバイス上判定のトラブルシューティング方法を教えてください。
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: a73525a7c2096235d583f54865fcdcbc4b36e7c0
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---

# at.jsのオンデバイス判定のトラブルシューティング

at.js JavaScriptライブラリを使用して、Adobe Targetのオンデバイス判定のトラブルシューティングを行うには、次の手順を実行します。

1. at.jsのコンソールログの有効化
1. ブラウザーの[ネットワーク]タブで、ルールアーティファクトのダウンロードを確認します。
1. at.jsカスタムイベントを使用したルールアーティファクトのダウンロードの検証

以下の各項では、各手順について詳しく説明します。

## 手順1:at.jsのコンソールログの有効化

URLパラメーター`mboxDebug=1`を追加すると、at.jsはブラウザーのコンソールにメッセージを印刷できます。

便利な概要を示すため、すべてのメッセージにプレフィックス「AT:」が付いています。 アーティファクトが正常に読み込まれたことを確認するには、コンソールログに次のようなメッセージが含まれている必要があります。

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

次の図に、コンソールログに表示されたメッセージを示します。

![アーティファクトメッセージを含むコンソールログ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## 手順2:ブラウザーの[ネットワーク]タブで、ルールアーティファクトのダウンロードを確認します。

ブラウザーの「ネットワーク」タブを開きます。

例えば、Google Chromeで開発ツールを開くには：

1. Ctrl + Shift + Jキー(Windows)またはCommand + Option + Jキー(Mac)を押します。
1. 「ネットワーク」タブに移動します。
1. キーワード「rules.json」で呼び出しをフィルターし、アーティファクトのルールファイルのみが表示されるようにします。

   また、「/配信|rules.json/」でフィルタリングして、すべての[!DNL Target]呼び出しとartifact rules.jsonを表示できます。

   ![Google Chromeの「ネットワーク」タブ](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## 手順3:at.jsカスタムイベントを使用したルールアーティファクトのダウンロードの検証

at.jsライブラリは、2つの新しいカスタムイベントをディスパッチして、オンデバイスの判定をサポートします。

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

購読すると、アーティファクトルールファイルのダウンロードが成功または失敗した場合のアクションを実行するために、アプリケーション内のこれらのカスタムイベントをリッスンできます。

次の例は、アーティファクトのダウンロードの成功と失敗のイベントをリッスンするコードの例を示しています。

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
