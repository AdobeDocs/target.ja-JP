---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 96%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2024年1月22日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## ブラウザーオーディエンス属性からの iPad と iPhone の非推奨（廃止予定）（2024年4月30日（PT））

| 非推奨（廃止予定） | 詳細 |
|--- |--- |
| [!DNL iPad] と [!DNL iPhone] は、オーディエンスの作成時に使用する[ブラウザー属性](/help/main/c-target/c-audiences/c-target-rules/browser.md)から非推奨（廃止予定）になります。<p>非推奨日（廃止予定日）：<P>2024年4月30日（PT） | [!DNL Adobe Target] を使用すると、ページを訪問した際に特定の[ブラウザーやブラウザーオプション](/help/main/c-target/c-audiences/c-target-rules/browser.md)を使用するユーザーなど、[いくつかのカテゴリ属性のいずれかをターゲットに設定](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)できます。<P><B>2024年4月30日（PT）以降、iPad と iPhone は、オーディエンスのカテゴリを作成する際に使用可能な[!UICONTROL ブラウザー]タイプのプルダウンリストから削除されます。</b><P>[!UICONTROL ブラウザー]属性を使用して iPad または iPhone をターゲットに設定するオーディエンスがある場合、これらのオーディエンスが引き続き期待どおりに機能するように、2024年4月30日（PT）までにこれらの設定を変更する必要があります。<p>代替設定の例については、 [ブラウザーオーディエンス属性からのiPadおよびiPhoneの廃止（2024 年 4 月 31 日）](/help/main/c-target/c-audiences/c-target-rules/browser.md#deprecation). |

## [!DNL Target] Standard／Premium 24.1.1（2024年1月22日、23日、25日（PT））

このリリースは、次の日に予定されています。

* **1月22日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **1月23日（PT）**：アジア太平洋（APAC）地域
* **1月25日（PT）**：アメリカ地域

このリリースには、以下の機能強化および修正が含まれています。

* 売上高目標指標を含む [!UICONTROL Analytics for Target]（A4T）アクティビティでは、レポートに列名として「売上高」が表示されず、売上高指標が（$）形式で表示されませんでした。これは、表面上の問題で、既に修正されています。（TGT-46995）
* レポートの日付間隔が正しく機能しない問題を修正しました。（TGT-47396）
* お客様が「[!UICONTROL その他のアクション]」アイコンを使用してアクティビティをアクティブ化または非アクティブ化した後、[!UICONTROL すべてのアクティビティ]ページに正しくないステータスが表示される問題を修正しました。（TGT-47367）
* [!UICONTROL 重要な属性]レポートが 1 人のお客様に対して表示されない問題を修正しました。（TGT-47272）
* 1 人のお客様が「認証が必要」を有効にしようとした際に「無効なペイロード」メッセージが表示される問題を修正しました。（TGT-47195）
* [!DNL Target] UI の多数のローカライズされた文字列を更新しました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
