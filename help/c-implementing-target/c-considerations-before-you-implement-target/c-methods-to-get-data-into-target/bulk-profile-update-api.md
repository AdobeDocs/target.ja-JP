---
keywords: 実装；実装；設定；設定；一括プロファイルの更新
description: 一括プロファイル更新APIを使用してターゲットにデータを取り込みます。
title: 一括プロファイル更新APIを使用してターゲットにデータを取り込む方法を教えてください。
feature: Implementation
role: Developer
exl-id: 068658fc-7082-425a-87c1-dd0de03cdc71
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 78%

---

# プロファイル一括更新 API

API経由で、多くの訪問者の訪問者プロファイルの更新を含む.csvファイルを[!DNL Adobe Target]に送信します。 各訪問者プロファイルでは、1 回の呼び出しで複数のページ内プロファイル属性を更新できます。

このオプションは、少し異なる顧客属性に似ています。

* 顧客属性では FTP アップロードを使用しますが、Target のプロファイル一括更新 API では HTTP POST API を使用します。
* 顧客属性データは Analytics と共有できます。プロファイルの一括更新は Target のみで使用できます。
* 顧客属性の場合は、Target がまだ認識していないユーザーのプロファイルも作成できます。プロファイル一括更新 API では、既存の Target プロファイルのみが更新されます。
* 顧客属性の場合は Experience Cloud ID（ECID）を使用する必要があります。プロファイル一括更新 API では、TNT ID または `mbox3rdPartyId` が必要です。
* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

## 形式

.csv ファイルでは、各訪問者を Target PCID または mboxThirdPartyId で参照する必要があります。Experience Cloud ID（ECID）には対応していません。すべてのプロファイル属性／値は、API を介して作成および更新されます。形式の詳細については、API ドキュメントを参照してください。

## 使用例の例

ページの実装でプロファイルデータを公開することなく、CRM やその他の社内システムに、一貫して更新して Target に送信したい有用な訪問者データを保管します。

## 方法の利点

プロファイル属性の数に上限がありません。

サイトを介して送信されるプロファイル属性を、API を介して更新できます（その逆も可能です）。

## 注意事項

バッチファイルの容量は 50 MB 未満にする必要があります。また、1 回にアップロードできる行数は 50 万行までです。

以降のバッチで、24 時間以内にアップロードできる回数や行数に上限はありません。ただし、他のプロセスを効率的に実行するために、営業時間中は取り込みプロセスが調整される場合があります。

合間に mbox を呼び出すことなく、連続する [V2 一括更新呼び出し（](https://developers.adobetarget.com/api/#updating-profiles)）を同じ thirdPartyIds に対しておこなうと、最初の一括更新呼び出しで更新されたプロパティは上書きされます。

## コードの例

[プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)を参照してください。

### 関連情報へのリンク

[プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)