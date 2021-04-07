---
keywords: 実装；実装；設定；設定；単一プロファイルの更新
description: 単一のプロファイル更新APIを使用してターゲットにデータを取得します。
title: 単一のプロファイル更新APIを使用してターゲットにデータを取り込む方法を教えてください。
feature: 実装
role: Developer
translation-type: tm+mt
source-git-commit: e8c25685341319fea4381386cad1ce0c5b80face
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 41%

---

# 単一プロファイル更新 API

一括プロファイル更新APIとほとんど同じですが、API呼び出しの行で、.csvファイルではなく1つの訪問者プロファイルが一度に更新されます。

## 形式

訪問者は、Target の mboxPC または mboxThirdPartyId の値によって識別する必要があります。Experience Cloud ID（ECID）には対応していません。

## 使用例

訪問者が何らかのオフライン操作を実行したときに、ターゲットをリアルタイムで更新する場合。 アクションには、コールセンターへの連絡、ローンの資金調達、店頭のロイヤルティカードを使用した使用、キオスクへのアクセスなどが含まれます。

## 方法の利点

プロファイル属性の数に上限がありません。

サイトを介して送信されるプロファイル属性を、API を介して更新できます（その逆も可能です）。

## 注意事項

24 時間ごとの API 呼び出しの上限は 100 万件です。

プロファイルのみが更新されます。Target がまだ認識していない潜在的なユーザーのプロファイルを作成することはできません。

## コードの例

GETとPOSTがサポートされます。`https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

## 関連情報へのリンク

[プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)