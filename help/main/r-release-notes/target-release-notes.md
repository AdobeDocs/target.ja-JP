---
keywords: リリースノート;リリース;更新;今後のリリース;機能強化;新機能;修正;アップデート;プレリリース
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の次回のリリースに含まれている新機能、機能強化および修正について説明します。
title: 次回の [!DNL Target] リリースには、どのような新機能や機能強化が含まれていますか？
feature: Release Notes
exl-id: f2783042-f6ee-4f73-b487-ede11d55d530
source-git-commit: 78bedce2134061edc48baf7023107e1dd48da2a1
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 50%

---

# [!DNL Target]リリースノート（プレリリース）

この記事には、SDK、API、JavaScript ライブラリなど、次回の [!DNL Adobe Target] リリースのプレリリース情報が含まれています。

**最終更新日：2023年1月16日（PT）**

>[!NOTE]
>
>リリース日、機能などの情報は、予告なく変更されることがあります。
>
>最新のリリースに関する情報を確認するには、[Target リリースノート](release-notes.md)を参照してください。これらのページの情報は、リリースのタイミングによって異なる場合があります。括弧内の問題番号は [!DNL Adobe] 内部で使用されます。

## ブラウザーオーディエンス属性からのiPadおよびiPhoneの廃止（2024 年 4 月 31 日）

| 廃止 | 詳細 |
|--- |--- |
| [!DNL iPad] および [!DNL iPhone] 廃止される [ブラウザー属性](/help/main/c-target/c-audiences/c-target-rules/browser.md) オーディエンスを作成する際に使用します。<p>廃止日：<P>2024 年 4 月 31 日 | [!DNL Adobe Target] 以下が可能です。 [複数のカテゴリ属性のいずれかに対するターゲット](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)( 特定の [ブラウザーまたはブラウザーのオプション](/help/main/c-target/c-audiences/c-target-rules/browser.md) 訪問者がページを訪問したとき。<P><B>2024 年 4 月 30 日以降、iPadとiPhoneは、使用可能な [!UICONTROL ブラウザー] タイプのドロップダウンリスト（オーディエンスのカテゴリを作成する場合）</b><P>iPad または iPhone をターゲットにするオーディエンスがある場合は、 [!UICONTROL ブラウザー] 属性内で設定を変更する場合、これらのオーディエンスが引き続き期待どおりに機能するように、2024 年 4 月 30 日より前にこれらの設定を変更する必要があります。<P>今後は、次の設定を使用する必要があります。<ul><li>[!UICONTROL モバイル] > [!UICONTROL タブレット]<P>![モバイルはタブレットです](/help/main/r-release-notes/assets/is-tablet.png)</li><li>[!UICONTROL モバイル] > [!UICONTROL デバイスのマーケティング名] [!UICONTROL 一致する] [!DNL iPad]<P>![iPad](/help/main/r-release-notes/assets/ipad.png)</li><li>[!UICONTROL モバイル] > [!UICONTROL デバイスのマーケティング名] [!UICONTROL 一致する] [!DNL iPhone]<p>![iPhone](/help/main/r-release-notes/assets/iphone.png)</li></ul> |

## [!DNL Target] Standard/Premium 24.1.1（2024 年 1 月 23 日および 25 日）

このリリースは、次の日に予定されています。

* **1月22日（PT）**：ヨーロッパ、中東、アフリカ（EMEA）地域
* **1月23日（PT）**：アジア太平洋（APAC）地域
* **1月25日（PT）**：アメリカ地域

このリリースには、以下の機能強化および修正が含まれています。

* レポートの日付間隔が正しく機能しない問題を修正しました。 （TGT-47396）
* 間違ったステータスが [!UICONTROL すべてのアクティビティ] を使用してアクティビティをアクティブ化または非アクティブ化した後のページ [!UICONTROL その他のアクション] アイコン。 （TGT-47367）
* 次の問題を修正しました： [!UICONTROL 重要な属性] 1 人の顧客に対して表示しないレポート。 （TGT-47272）
* あるお客様が「認証が必要」を有効にしようとすると、「無効なペイロード」メッセージが表示される問題を修正しました。 （TGT-47195）
* 内の多数のローカライズされた文字列を更新しました。 [!DNL Target] UI

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## プレリリース情報 {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

[!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションの今後の製品強化に関する事前通知を受信するには、[!DNL Adobe Priority Product Update] に新規登録します。

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
