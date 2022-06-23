---
keywords: 実装；実装する；設定；設定；単一のプロファイルの更新
description: データをに取り込む [!DNL Target] 単一のプロファイル更新 API を使用する。
title: データをに取り込む方法 [!DNL Target] 単一プロファイル更新 API を使用する場合
feature: Implementation
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 44%

---

# 単一プロファイル更新 API

プロファイル一括更新 API とほとんど同じですが、API 呼び出しで、 .csv ファイルではなく、1 人の訪問者プロファイルが一度に更新されます。

## 形式

訪問者は、Target の mboxPC または mboxThirdPartyId の値によって識別する必要があります。Experience Cloud ID（ECID）には対応していません。

## 使用例

訪問者が何らかのオフラインアクションを実行したときに、リアルタイムで Target を更新したい。 アクションには、コールセンターへのリーチ、ローンの資金提供、店舗内のロイヤルティカードを使用したキオスクへのアクセスなどが含まれます。

## 方法の利点

プロファイル属性の数に上限がありません。

サイトを介して送信されるプロファイル属性を、API を介して更新できます（その逆も可能です）。

## 注意事項

24 時間ごとの API 呼び出しの上限は 100 万件です。

プロファイルのみが更新されます。Target がまだ認識していない潜在的なユーザーのプロファイルを作成することはできません。

## コード例

GETとPOSTがサポートされます。 `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)

