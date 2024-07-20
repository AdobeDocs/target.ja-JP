---
keywords: リリースノート;新機能;リリース;アップデート;アップデート;リリース;機能強化;機能強化;修正;バグ修正;アップデート
description: SDK、API、JavaScript ライブラリなど、 [!DNL Adobe Target] の現在のリリースに含まれている新機能、機能強化および修正について説明します。
landing-page-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
short-description: ' [!DNL Adobe Target] の現在のリリースに含まれる新機能、機能強化、修正点について説明します。'
title: 現在のリリースの内容
feature: Release Notes
exl-id: 3ffead4f-113c-4153-b0b1-fc2aff710063
source-git-commit: 44445f269a69a3ac3e3bc88bab8abf9fc4d51663
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 100%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Adobe Customer Journey Analytics] での [!DNL Target] レポート（2024年5月8日（PT））

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/customer-journey-analytics){target=_blank} と [!DNL Target] の統合では、組織の最適化プログラムに適した強力な分析機能と時間節約ツールを利用できます。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは、[実験パネル](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}などの [!DNL Customer Journey Analytics] 機能を活用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、[[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/ja/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} および [!DNL Target] のレポートを単一のソースで作成できます。両方のパーソナライゼーション製品を [!DNL Customer Journey Analytics] に接続すると、web パーソナライゼーションの全体像を把握できます。

詳しくは、[Adobe Customer Journey Analytics での Target レポート](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md)を参照してください。

## [!UICONTROL Visual Experience Composer] ヘルパー拡張機能（2024年4月23日（PT））

従来の [!DNL Target] Visual Experience Composer ヘルパー拡張機能は、Manifest V2 を使用して作成されました。[!DNL Google] では、2024年6月以降、Manifest V2 を使用して作成された拡張機能を許可しなくなると発表しました。詳しくは、[[!UICONTROL Visual Experience Composer] ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を参照してください。

[!DNL Adobe] では、お客様ができるだけ早く新しい [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md)に移行することをお勧めします。

## [!UICONTROL Browser] オーディエンス属性の `Browser:iPad` と `Browser:iPhone` の更新（2024年4月30日（PT））

| アップデート | 詳細 |
|--- |--- |
| オーディエンスの作成時に使用される[ブラウザー属性](/help/main/c-target/c-audiences/c-target-rules/browser.md)で [!UICONTROL Browser:iPad] と [!UICONTROL Browser:iPhone] が更新されました。 | [!DNL Adobe Target] を使用すると、ページを訪問した際に特定の[ブラウザーやブラウザーオプション](/help/main/c-target/c-audiences/c-target-rules/browser.md)を使用する訪問者など、[いくつかのカテゴリ属性のいずれかをターゲットに設定](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)できます。<P>[!DNL Target] Standard／Premium 24.3.1（2024年3月4～6日（PT））以降、`Browser:iPad` や `Browser:iPhone` などのターゲット UI を使用して作成された組み込みオーディエンスは、`profile.mobile.deviceVendor`、`profile.mobile.isMobilePhone`、`profile.mobile.isTablet` を使用して [!DNL iPad] と [!DNL iPhone] に対して適切なターゲティングを実行するように更新されます。<P>このアップデートでは、お客様側でのアクションは必要ありません。<p><B>重要</b>：お客様がプロファイルスクリプト（および JavaScript セグメント）で [!DNL iPad] と [!DNL iPhone] を適切にターゲティングを実行するには、**2024年4月30日（PT）**&#x200B;までにお客様が手動で変更を行う必要があります。手動で変更する必要がある代替設定の例については、[[!UICONTROL Browser] オーディエンス属性の  [!DNL iPad]  と  [!DNL iPhone]  のアップデート](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates)を参照してください。 |

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
