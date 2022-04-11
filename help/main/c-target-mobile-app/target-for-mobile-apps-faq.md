---
keywords: モバイルアプリ；よくある質問；faq;target モバイルアプリ
description: よくある質問とその回答をAdobe [!DNL Target] （モバイルアプリ用）
title: に関するよくある質問 [!DNL Target] モバイルアプリ用？
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 3%

---

# モバイルアプリ用 Target に関する FAQ

に関するよくある質問のリスト [!DNL Target] （モバイルアプリ用）

## でタグを使用する必要がある [!DNL Adobe Experience Platform] :SDK をデプロイする場合、またはを使用せずに SDK をデプロイする場合は、 [!DNL Launch]?

SDK は、 [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). を使用しない場合、 [Adobe Experience Platformのタグ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=ja)を使用する場合は、独自の設定ファイルを管理し、アプリで管理する必要があります。

## 現在利用可能な SDK を教えてください。

Adobe Experience Platform Mobile SDK は、現在、iOS、Android および React をサポートしています。 詳しくは、 [Adobe Experience Cloud Platform Mobile SDK ガイド](https://aep-sdks.gitbook.io/docs/).

## 緯度と経度に関する検証の観点から、位置ベースの機能の頻度はどれくらいですか？

詳しくは、 [AdobePlaces Service ドキュメント](https://experienceleague.adobe.com/docs/places/using/home.html) を参照してください。

## Adobe Experience Platform Mobile SDK を動作させるには at.js が必要ですか？

いいえ。モバイル SDK を使用するのに at.js は必要ありません。 at.js は [!DNL Target] Web サイト用の JavaScript ライブラリ。 Adobe Experience Platform Mobile SDK は、モバイルアプリ用です。

## 次に該当 [!DNL Target] モバイルとAdobe [!DNL Target] Premium 製品 SKU のみ？

いいえ。の場合 [!DNL Adobe Target Standard] のお客様は、A/B テストおよびエクスペリエンスターゲット設定 (XT) アクティビティに Mobile SDK を使用できるのは、 [!DNL Target Standard] モバイルアプリのアドオン。 モバイルアプリでRecommendationsまたは AI を利用した機能を使用する場合は、 [Adobe Target Premium](/help/main/c-intro/intro.md#premium) ライセンス。

## Adobe Experience Manager(AEM) と [!DNL Target] モバイルアクティビティ？

ロードマップ上にありますが、まだタイムラインがありません。 現在、JSON を共有できます [エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) AEMから Target に移行した後、モバイルアプリアクティビティで使用できる場合があります。
