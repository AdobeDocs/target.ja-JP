---
keywords: トラブルシューティング。指標の相違、FAQ、レポート
description: Adobe Target のレポートに関するよくある質問のリストです。
title: Adobe Target のレポートの FAQ
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# レポートの FAQ{#reporting-faq}

[!DNL Target] のレポートに関するよくある質問のリストです。

## [!UICONTROL エクスペリエンスターゲット設定]（XT）レポートにコントロールエクスペリエンス用の指標が含まれているのはなぜですか？

XT アクティビティには、常にコントロールエクスペリエンスがある必要があります。[!UICONTROL A/B テスト]アクティビティと同様の方法で XT アクティビティを使用している場合（かなり一般的なシナリオ）、コントロールエクスペリエンスデータが使用されます。レポートで有用でないとわかった場合、コントロールエクスペリエンスデータを無視できます。

## 他の [!DNL Adobe Experience Cloud] ソリューションと比較して [!DNL Target] の訪問数が低いのはなぜでしょうか。{#section_7E626FDB417E41B8B58BBF30FB207409}

[!DNL Target] が報告する訪問などの指標の数値が、他の [!DNL Experience Cloud] ソリューションが報告する数値よりも常に低いのには多数の理由があります。

* [!DNL Target] はアクティビティに該当する訪問者のみの訪問数を数えます。他のソリューションは、訪問者をページに導いたアクティビティが何であったかに関わらず、ページを表示する訪問者の訪問を数えます。
* 異なるアクティビティが同じ場所（相互に排他的）を競い合う場合もあります。その結果、訪問者は Web ページ上で異なるコンテンツを見ることになり、[!DNL Target] が報告する指標の数値に影響します。

## アクティビティのレポートにデータがないのはなぜでしょうか。{#section_E4722F6445884130951DF79981C8289B}

アクティビティの内容がユーザーに配信されたのにそのレポートにデータがない場合は、レポート設定で正しい環境（[ホストグループ](/help/administrating-target/hosts.md)）を選択するようにしてください。

開発環境が選択されていると、「選択されたレポート設定ではデータがありません」と言うエラーメッセージが表示される場合があります。

アクティビティのレポートの環境を変更するには：

1. 「**[!UICONTROL アクティビティ]**」をクリックし、リストで目的のアクティビティをクリックし、「**レポート[!UICONTROL 」タブをクリックします。]**
1. 歯車アイコンをクリックし、レポート設定を変更します。

   ![A/B 設定ダイアログボックス](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >歯車アイコンは、[!UICONTROL Automated Personalization] レポートでは使用できません。

1. **[!UICONTROL Environment]** ドロップダウンリストで **[!UICONTROL 、「Production]**」を選択します。

   開発環境を選択していると、レポートのデータが使用できない場合があります。

1. 「**[!UICONTROL 保存]**」をクリックします。

環境について詳しくは、[ホスト](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E)を参照してください。
