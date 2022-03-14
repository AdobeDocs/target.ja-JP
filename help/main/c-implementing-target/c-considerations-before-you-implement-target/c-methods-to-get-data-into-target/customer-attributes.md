---
keywords: 実装；実装する；設定；設定；顧客属性
description: データをに取り込む [!DNL Target] 顧客属性を使用する。
title: データをに取り込む方法 [!DNL Target] 顧客属性を使用している場合
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 51%

---

# 顧客属性

顧客属性を使用すると、FTP を使用して訪問者プロファイルデータを [!DNL Adobe Experience Cloud]. アップロード後は、 [!DNL Adobe Analytics] および [!DNL Adobe Target].

Target Standard のお客様は 5 つの属性を適用でき、Target Premium のお客様は 200 の属性を適用できます。

## 形式

Experience Cloud ID（ECID）および属性の名前と値のペアを含む .csv ファイルは、FTP を介してアップロードするか、Experience Cloud の UI を使用して手動でアップロードします。

## 使用例

Target や Analytics など、Adobe Experience Cloud と共有したい有用な情報を、CRM やその他の社内システムに保管します。

## 方法の利点

顧客データをアップロードすると、Target がまだ認識していない訪問者でも、その訪問者のプロファイルのエントリが Target に作成されます。

Target と Analytics で自動的にデータが同期化されます。

FTP は、API よりもシンプルな実装方法です。

## 注意事項

Target Standard のお客様は 5 つの属性を適用でき、Target Premium のお客様は 200 の属性を適用できます

ページではなく、顧客属性でのみ値を更新できます。

Experience Cloud ID（ECID）の実装が必要です。

## コード例

詳しくは、 [顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### 関連情報へのリンク

[顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
