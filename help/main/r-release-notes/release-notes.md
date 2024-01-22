---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 99152f66217f66174e8b6a5a7319f11b22c74b8e
workflow-type: tm+mt
source-wordcount: '575'
ht-degree: 84%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

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

* [!UICONTROL Analytics for Target] (A4T) 売上高目標指標を含むアクティビティで、列名に「売上高」が表示されず、売上高指標がレポートの ($) 形式で表示されませんでした。 これは化粧上の問題で、修正されました。 （TGT-46995）
* レポートの日付間隔が正しく機能しない問題を修正しました。（TGT-47396）
* お客様が「[!UICONTROL その他のアクション]」アイコンを使用してアクティビティをアクティブ化または非アクティブ化した後、[!UICONTROL すべてのアクティビティ]ページに正しくないステータスが表示される問題を修正しました。（TGT-47367）
* 次の問題を修正しました： [!UICONTROL 重要な属性] 1 人の顧客に対して表示しないレポート。 （TGT-47272）
* 1 人の顧客が「認証が必要」を有効にしようとすると、「無効なペイロード」メッセージが表示される問題を修正しました。 （TGT-47195）
* [!DNL Target] UI の多数のローカライズされた文字列を更新しました。

## その他のリリースノートとバージョンの詳細

| リソース | 詳細 |
|--- |--- |
| [リリースノート：Adobe Target Platform Experience Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=ja) | Platform Web SDK の各バージョンの変更点に関する詳細です。 |
| [at.js のバージョンの詳細](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} | [!DNL Adobe Target] at. js JavaScript ライブラリの各バージョンの変更点についての詳細です。 |

## ドキュメントの変更、過去のリリースノートおよび Experience Cloud リリースノート

追加情報については、各リリースのリリースノートに加えて、以下のリソースを参照してください。

| リソース | 詳細 |
|--- |--- |
| [ドキュメントの変更点](/help/main/r-release-notes/doc-change.md) | リリースノートに記載されていない、このガイドの更新点に関する詳細情報を表示します。 |
| [以前のリリースのリリースノート](/help/main/r-release-notes/release-notes-for-previous-releases.md)。 | 以前のリリースの Target Standard および Target Premium の新機能および拡張機能に関する情報を確認できます。 |
| [Adobe Experience Cloud のリリースノート](https://experienceleague.adobe.com/docs/release-notes/experience-cloud/current.html?lang=ja){target=_blank} | Adobe Experience Cloud ソリューションの最新のリリースノートが表示されます。 |

## プレリリース情報 {#section_5D588F0415A2435B851A4D0113ACA3A0}

以下のリソースでは、以下の Target リリースの内容を確認できます。

| リソース | 詳細 |
|--- |--- |
| [アドビ優先製品アップデート](https://www.adobe.com/subscription/priority-product-update.html){target=_blank} | [!DNL Target] およびその他の [!DNL Adobe Experience Cloud] ソリューションに対する今後の製品の機能強化に関する事前通知を受信します。 |
| [Target リリースノート - プレリリース](/help/main/r-release-notes/target-release-notes.md){target=_blank} | プレリリース情報など、当月の Target リリースに関する情報です。 |
