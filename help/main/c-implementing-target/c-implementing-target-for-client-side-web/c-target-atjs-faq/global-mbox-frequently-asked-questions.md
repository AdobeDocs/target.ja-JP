---
keywords: トラブルシューティング;よくある質問;FAQ;グローバル;グローバル mbox
description: よくある質問 (FAQ) と回答を読むAdobe [!DNL Target] グローバル mbox。
title: グローバル mbox に関するよくある質問は何ですか。
feature: at.js
role: Developer
exl-id: ec8399df-5222-44bd-9e61-dfce8fd1694d
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 81%

---

# グローバル mbox に関するよくある質問

グローバル mbox に関するよくある質問（FAQ）のリストです。

## 複数のグローバル mbox を使用できる ( [!DNL Target] アカウントが複数のドメインにまたがって設定されているか {#section_B7252BA6C3BB4EF4AE9E53F47FD58ABD}

アカウント全体で使用できるグローバル mbox は 1 つだけです。

アクティビティに URL ルールを追加することで、アクティビティの実行場所を制限できます。詳しくは、[類似のページに同じエクスペリエンスを組み込む](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781)を参照してください。

また、[targetPageParams](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) を使用し、これらのパラメーターを [!UICONTROL Visual Experience Composer]（VEC）の「URL を設定」セクションで選択するか、このパラメーターをフォームベースの Experience Composer で「絞り込み条件」として追加することで、ページにパラメーターを渡せます。

## 売上高データを [!DNL Target] グローバル mbox? {#section_17AEA933BADA4D169CCEDF5833C41306}

target-global-mbox で売上高と注文の情報を収集するには、「mbox パラメーター」を Target に送信する必要があります。このパラメーターは名前と値のペアで、Target により多くの情報を送信するために使用します。Target はこれらのパラメーター（予約された名前）を自動的に検索し、売上高データを設定します。

`orderConfirmPage` の場合、`orderTotal`、`orderId`、および `productPurchasedId` を渡す必要があります。

これらのパラメーターは、 `targetPageParams()`. 詳しくは、「[グローバル mbox にパラメーターを渡す](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5)」を参照してください。

以下のように、注文確認ページが表示された場合のみ Target が target-global-mbox でコンバージョンをカウントするよう、コンバージョンページに対するターゲット設定を追加することもお勧めします。

![](assets/revenue1.png)

上図の「サイトのページ」セクションの選択内容は、「現在のページ」、「URL」、「次を含む」、「orderconfirm」となっています。

![](assets/revenue2.png)

上図のオプションは、以下の設定で構成されています。

* **このアクティビティでは何を測定しますか？：**&#x200B;売上高
* **レポートのデフォルトの表示：**&#x200B;訪問者あたりの売上高（RPV）
* **目標を達成したことを示すオーディエンスのアクションは何ですか？** mbox が表示された、target-global-mbox