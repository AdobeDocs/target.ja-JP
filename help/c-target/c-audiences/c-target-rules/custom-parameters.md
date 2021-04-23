---
keywords: カスタムパラメーター、targetカスタムパラメーター、targetpageparams、ターゲットmboxパラメーター
description: オーディエンスで使用するAdobe [!DNL Target] にカスタムパラメーターを渡す方法を説明します。
title: カスタム訪問者ーに基づいてI [!DNL Target] パラメーターを作成できますか。
feature: オーディエンス
exl-id: f0669888-6b9e-4738-9ed4-0418ea56fffa
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 85%

---

# カスタムパラメーター

カスタムパラメーターは、mbox パラメーターです。mbox に対して mbox パラメーターを渡した場合、または targetPageParams 関数を使用した場合、それらのパラメーターはここに表示され、オーディエンスで使用できます。

詳しくは、[グローバルmboxにパラメーターを渡す](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md)を参照してください。

mbox パラメーターに基づいてカスタムオーディエンスを作成しているときに、`mboxParameter` で `mboxName` の入力が求められなくなりました。mbox 名はオプションになりました。この変更により、複数の mbox のパラメーターを使用することや、まだエッジで記録されていないパラメーターを参照することができます。

1. [!DNL Target] インターフェイスで、**[!UICONTROL オーディエンス]**／**[!UICONTROL オーディエンスを作成]**&#x200B;をクリックします。
1. オーディエンスに名前を付けます。
1. **[!UICONTROL ルール]**&#x200B;追加/**[!UICONTROL カスタム]**&#x200B;をクリックします。

   目的のパラメーターを選択するには：

   * 新しいオーディエンスを作成する場合、リストからパラメーター名を選択するか、特定のパラメーター名の最初の文字を入力するか、または特定のパラメーター名の完全な名前を入力します。
   * mbox 名は覚えているが、パラメーター名は覚えていないという場合は、チェックボックスを使用して、目的のパラメーターを渡す既知の mbox に関してフィルタリングをおこないます。

   いずれの方法でも、mbox とパラメーターの間にリンクはありません。オーディエンスは、該当するパラメーターを渡す mbox すべてに対して、パラメーターに基づいて機能します。

   既存のオーディエンスを編集すると、作成時に指定された mbox 名と共にフィルタリング条件が表示されます。

1. 評価基準を選択します。

   * 次を含む（大文字と小文字を区別しない）
   * 次を含まない（大文字と小文字を区別しない）
   * 次と等しい

   ![カスタムパラメーターオーディエンス](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. 新しい行に各値を入力します。
1. （オプション）「**[!UICONTROL ルールを追加]**」をクリックして、オーディエンス用の追加のルールを設定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

オーディエンスの[ポップアップカード内の定義の詳細](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780)には、「Rules」セクションにパラメーター名が表示されます。フィルタリングに使用する mbox への参照はありません。

>[!NOTE]
>
>Target 18.5.1 リリース（2018 年 5 月 23 日）より前に作成されたカスタムオーディエンスの場合、mbox 名はオーディエンスの定義ポップアップカードに表示されません。mbox 名がカードに表示されるようにするには、カスタムオーディエンスを保存し直す必要があります。

## 注意点 {#considerations}

* オーディエンスおよびアクティビティは、特定の mbox 用に評価されます。例えば、グローバル mbox が特定のパラメーターを渡すが、リージョナル mbox は渡さない場合、そのパラメーターをターゲットにしたアクティビティ／オーディエンスでは、リージョナル mbox は対象になりません。
* ターゲット設定は、mboxPC、mboxSession、mbox3rdPartyId、mboxMCSDID、mboxMCAVID、mboxMCGVID、mboxMCGVID、mboxCount、mboxId、mboxVersionなどの内部mboxパラメーターでは評価されません。

## トレーニングビデオ：オーディエンスの作成![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
