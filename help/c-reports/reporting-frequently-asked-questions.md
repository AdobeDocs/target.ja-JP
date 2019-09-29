---
description: Target のレポートに関するよくある質問のリストです。
keywords: トラブルシューティング。指標の相違、FAQ、レポート
seo-description: Adobe targetのレポートに関するよくある質問のリストです。
seo-title: Adobe targetのレポートFAQ
solution: 'Target '
title: レポートの FAQ
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: a6f2eceaddf67653b36a1687ba071f7226169516

---


# レポートの FAQ{#reporting-faq}

[!DNL Target] のレポートに関するよくある質問のリストです。

## エクスペリエンスのターゲ [!UICONTROL ット設定] (XT)レポートにコントロールエクスペリエンスの指標が含まれるのはなぜですか。

XTアクティビティは常にコントロールのエクスペリエンスを持つ必要があります。 XTアクティビティを [!UICONTROL A/B Test] （かなり一般的なシナリオ）と同様の方法で使用している場合は、コントロールエクスペリエンスのデータが役に立ちます。 コントロールエクスペリエンスのデータがレポートで役に立たない場合は、そのデータを無視できます。

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

[!DNL Target] が報告する訪問などの指標の数値が、他の [!DNL Experience Cloud] ソリューションが報告する数値よりも常に低いのには多数の理由があります。

* [!DNL Target] はアクティビティに該当する訪問者のみの訪問数を数えます。他のソリューションは、訪問者をページに導いたアクティビティが何であったかに関わらず、ページを表示する訪問者の訪問を数えます。
* 異なるアクティビティが同じ場所（相互に排他的）を競い合う状況が発生する可能性があります。 その結果、訪問者は Web ページ上で異なるコンテンツを見ることになり、[!DNL Target] が報告する指標の数値に影響します。

## アクティビティのレポートにデータがないのはなぜでしょうか。{#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

開発環境が選択されていると、「選択されたレポート設定ではデータがありません」と言うエラーメッセージが表示される場合があります。

アクティビティのレポートの環境を変更するには：

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストで目的のアクティビティをクリックし、「**レポート[!UICONTROL 」タブをクリックします。]**
1. 歯車アイコンをクリックし、レポート設定を変更します。

   ![A/B設定ダイアログボックス](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. **[!UICONTROL Environment]** ドロップダウンリストで **[!UICONTROL 、「Production]**」を選択します。

   開発環境を選択していると、レポートのデータが使用できない場合があります。

1. 「**[!UICONTROL 保存]**」をクリックします。

環境について詳しくは [、「ホスト](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)」を参照してください。
