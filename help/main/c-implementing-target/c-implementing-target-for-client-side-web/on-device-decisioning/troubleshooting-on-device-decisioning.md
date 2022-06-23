---
keywords: 実装；javascript ライブラリ；js;atjs;on-device decisioning;on device decisioning;at.js;on-device;on-device；デバイス；トラブルシューティング；トラブルシューティング
description: at.js ライブラリを使用したオンデバイス判定のトラブルシューティング方法について説明します。
title: at.js JavaScript ライブラリを使用したオンデバイス判定のトラブルシューティング方法を教えてください。
feature: at.js
role: Developer
exl-id: 76bb9393-1560-455b-9d95-91576faee1f2
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---

# at.js のオンデバイス判定のトラブルシューティング

でオンデバイス判定をおこなう際のトラブルシューティングをおこなうには、次の手順を実行します。 [!DNL Adobe Target] at.js JavaScript ライブラリを使用する場合：

## 手順 1:at.js のコンソールログの有効化

URL パラメーターの追加 `mboxDebug=1` at.js がブラウザーのコンソールにメッセージを印刷できるようにします。

すべてのメッセージには、わかりやすい概要を示すために、プレフィックス「AT:」が付きます。 アーティファクトが正常に読み込まれるようにするには、コンソールログに次のようなメッセージが記録されます。

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

次の図は、これらのメッセージをコンソールログに表示しています。

![アーティファクトメッセージを含むコンソールログ](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## 手順 2:ブラウザーの「ネットワーク」タブで、ルールアーティファクトのダウンロードを確認します。

ブラウザーの「ネットワーク」タブを開きます。

例えば、Google Chrome で DevTools を開くには、次のようにします。

1. Ctrl + Shift + J キー (Windows) または Command + Option + J キー (Mac) を押します。
1. 「ネットワーク」タブに移動します。
1. キーワード「rules.json」で呼び出しをフィルタリングして、アーティファクトルールファイルのみが表示されるようにします。

   また、「/delivery|rules.json/」でフィルタリングして、すべての [!DNL Target] の呼び出しとアーティファクトの rules.json です。

   ![Google Chrome の「ネットワーク」タブ](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## 手順 3:at.js カスタムイベントを使用したルールアーティファクトのダウンロードの検証

at.js ライブラリは、オンデバイス判定をサポートするために、2 つの新しいカスタムイベントをディスパッチします。

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

アーティファクトルールファイルのダウンロードが成功または失敗した場合のアクションに対して、アプリケーションでこれらのカスタムイベントをリッスンするよう登録できます。

アーティファクトのダウンロードの成功イベントと失敗イベントをリッスンするコード例を次に示します。

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
