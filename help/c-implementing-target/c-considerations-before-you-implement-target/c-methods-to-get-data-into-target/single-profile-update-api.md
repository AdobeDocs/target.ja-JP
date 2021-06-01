---
keywords: 実装；実装する；設定；設定；単一プロファイルの更新
description: 単一のプロファイル更新APIを使用して [!DNL Target] にデータを取得します。
title: 単一のプロファイル更新APIを使用して [!DNL Target] にデータを取り込む方法を教えてください。
feature: 実装
role: Developer
exl-id: 8331866c-0b84-4d08-83b4-f7f82c67cd21
source-git-commit: 18b9a56b8aef2fdfb8a4431fec4ae3a65adcf067
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 42%

---

# 単一プロファイル更新 API

プロファイル一括更新APIとほとんど同じですが、訪問者プロファイルは、 .csvファイルではなく、API呼び出しで1回に1つずつ更新されます。

## 形式

訪問者は、Target の mboxPC または mboxThirdPartyId の値によって識別する必要があります。Experience Cloud ID（ECID）には対応していません。

## 使用例

訪問者が何らかのオフラインアクションを実行する際に、リアルタイムでTargetを更新したい場合。 アクションには、コールセンターへの連絡、ローンの資金提供、店舗内のロイヤルティカードを使用したロイヤリティーカードの使用、キオスクへのアクセスなどが含まれます。

## 方法の利点

プロファイル属性の数に上限がありません。

サイトを介して送信されるプロファイル属性を、API を介して更新できます（その逆も可能です）。

## 注意事項

24 時間ごとの API 呼び出しの上限は 100 万件です。

プロファイルのみが更新されます。Target がまだ認識していない潜在的なユーザーのプロファイルを作成することはできません。

## コード例

GETとPOSTがサポートされます。`https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

>[!MORELIKETHIS]
>
>* [プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)

