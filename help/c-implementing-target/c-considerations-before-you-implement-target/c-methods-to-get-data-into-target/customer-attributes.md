---
keywords: 実装；実装；設定；設定；顧客属性
description: 顧客属性を使用して、ターゲットにデータを取り込みます。
title: 顧客属性を使用してターゲットにデータを取り込む方法を教えてください。
feature: Implementation
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 51%

---

# 顧客属性

顧客属性を使用すると、訪問者プロファイルデータをFTP経由で[!DNL Adobe Experience Cloud]にアップロードできます。 アップロードが完了したら、[!DNL Adobe Analytics]と[!DNL Adobe Target]のデータを使用します。

Target Standardのお客様は5つの属性を適用でき、Target Premiumのお客様は200の属性を適用できます。

## 形式

Experience Cloud ID（ECID）および属性の名前と値のペアを含む .csv ファイルは、FTP を介してアップロードするか、Experience Cloud の UI を使用して手動でアップロードします。

## 使用例の例

Target や Analytics など、Adobe Experience Cloud と共有したい有用な情報を、CRM やその他の社内システムに保管します。

## 方法の利点

顧客データをアップロードすると、Target がまだ認識していない訪問者でも、その訪問者のプロファイルのエントリが Target に作成されます。

Target と Analytics で自動的にデータが同期化されます。

FTP は、API よりもシンプルな実装方法です。

## 注意事項

Target Standardのお客様は5つの属性を適用でき、Target Premiumのお客様は200の属性を適用できます

ページではなく、顧客属性でのみ値を更新できます。

Experience Cloud ID（ECID）の実装が必要です。

## コードの例

詳しくは、[顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html)を参照してください。

### 関連情報へのリンク

[顧客属性ソースの作成とデータファイルのアップロード](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
