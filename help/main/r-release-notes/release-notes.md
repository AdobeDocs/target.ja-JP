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
ht-degree: 58%

---

# [!DNL Target] リリースノート（最新）

これらのリリースノートは、[!DNL Adobe Target Standard] と [!DNL Target Premium] の各リリースの機能、機能強化および修正点について説明します。また、該当する場合は、[!DNL Target] API、SDK、[!DNL Adobe Experience Platform Web SDK]、JavaScript ライブラリ（at.js）およびその他のプラットフォームの変更に関するリリースノートも含まれます。

（括弧内の問題番号は [!DNL Adobe] 内部で使用するためのものです。）

## [!DNL Target] でのレポート [!DNL Adobe Customer Journey Analytics] （2024 年 5 月 8 日（PT））

～間の統合 [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} および [!DNL Target] は、組織の最適化プログラムに適した強力な分析ツールと時間節約ツールを提供します。

[!DNL Customer Journey Analytics] を [!DNL Target] のレポートソースとして使用する主なメリットは次のとおりです。

* マーケターは、[!DNL Customer Journey Analytics] の成功指標を [!DNL Target] のアクティビティレポートにいつでも動的に適用できます。アクティビティを実行する前にすべての項目を指定する必要はありません。
* マーケターは以下を活用できます [!DNL Customer Journey Analytics] などの機能 [実験パネル](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}を使用して、web サイトのパーソナライゼーションをさらに分析できます。
* マーケターは、のレポートソースを 1 つにまとめることができます [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/reporting/cja-ajo){target=_blank} および [!DNL Target]. 両方のパーソナライゼーション製品を [!DNL Customer Journey Analytics] に接続すると、web パーソナライゼーションの全体像を把握できます。

詳しくは、を参照してください [Adobe Customer Journey Analyticsでの Target レポート](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

## [!UICONTROL Visual Experience Composer] ヘルパー拡張機能（2024 年 4 月 23 日）

レガシー [!DNL Target] Visual Experience Composer ヘルパー拡張機能は、Manifest V2 を使用して作成されました。 [!DNL Google] 2024 年 6 月以降、Manifest V2 を使用して作成した拡張機能は許可されなくなると発表しました。 詳しくは、を参照してください [[!UICONTROL Visual Experience Composer] ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

[!DNL Adobe] では、お客様に新しいバージョンに移行することをお勧めします [Visual Editing Helper 拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) できるだけ早く。

## の更新 `Browser:iPad` および `Browser:iPhone` 。対象： [!UICONTROL Browser] オーディエンス属性（2024 年 4 月 30 日）

| 更新 | 詳細 |
|--- |--- |
| [!UICONTROL Browser:iPad] および [!UICONTROL Browser:iPhone] 更新日時 [ブラウザー属性](/help/main/c-target/c-audiences/c-target-rules/browser.md) オーディエンスの作成時に使用されます。 | [!DNL Adobe Target] 次のことができます [複数のカテゴリ属性のいずれかに対するターゲット](/help/main/c-target/c-audiences/c-target-rules/target-rules.md)特定のを使用する訪問者を含む [ブラウザーまたはブラウザーのオプション](/help/main/c-target/c-audiences/c-target-rules/browser.md) 訪問者がページにアクセスしたタイミング。<P>の概要 [!DNL Target] Standard/Premium 24.3.1 （2024 年 3 月 4～6 日（PT））:Target UI を使用して作成された組み込みオーディエンス（例：） `Browser:iPad` および `Browser:iPhone` は、適切なターゲティングを実行するように更新されます [!DNL iPad] および [!DNL iPhone] 使用 `profile.mobile.deviceVendor`, `profile.mobile.isMobilePhone` および `profile.mobile.isTablet`.<P>この更新は、顧客側でのアクションは必要ありません。<p><B>重要</b>：で適切なターゲティングを実行する顧客 [!DNL iPad] および [!DNL iPhone] プロファイルスクリプト（および JavaScript セグメント）では、顧客は次の手順で手動で変更する必要があります。 **2024 年 4 月 30 日（Pt）**. 手動で変更する必要がある代替設定の例については、を参照してください。 [の更新 [!DNL iPad] および [!DNL iPhone] 。対象： [!UICONTROL Browser] オーディエンス属性](/help/main/c-target/c-audiences/c-target-rules/browser.md#updates). |

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
