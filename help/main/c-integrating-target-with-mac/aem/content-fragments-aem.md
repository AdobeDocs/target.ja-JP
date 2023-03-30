---
keywords: エクスペリエンス；json;aem;adobe experience manager;adobe target への書き出し；コンテンツフラグメント；フラグメント；CF;cf；ヘッドレス；パーソナライゼーション；実験
description: 使用方法を学ぶ [!DNL Adobe Experience Manager] [!UICONTROL コンテンツフラグメント] in [!DNL Adobe Target] アクティビティ。
title: 使用方法 [!DNL Adobe Experience Manager] (AEM) [!UICONTROL コンテンツフラグメント]?
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html#beta newtab=true" tooltip="What are Target Beta release features?"
feature: Integrations
source-git-commit: 4dd74f10c4a6aa9b056ab9f528a38851576f38f7
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# AEM [!UICONTROL コンテンツフラグメント]

用途 [!UICONTROL コンテンツフラグメント] (CF) を [!DNL Adobe Experience Manager] (AEM) [!DNL Target] アクティビティを使用して、ヘッドレスなパーソナライゼーションと実験を支援します。

ヘッドレスパーソナライゼーションと実験のためのAEMコンテンツフラグメント

>[!NOTE]
>
>この機能は 2023 年 4 月 7 日にリリースされる予定です。

>[!NOTE]
>
>AEMを使用する際は、次の点に注意してください。 [!UICONTROL コンテンツフラグメント] in [!DNL Target]:
> 
>* この機能を使用するには、 [!DNL Adobe Experience Manager] (AEM) 顧客。 詳しくは、 [要件](#section_AE6F0971E1574B3AA324003599B96E5A) 下
>
>* この機能は、次のアクティビティタイプで使用できます。 [!UICONTROL A/B テスト], [!UICONTROL 自動配分], [!UICONTROL 自動ターゲット], [!UICONTROL Automated Personalization] (AP) および [!UICONTROL エクスペリエンスのターゲット設定] (XT)。 この機能は、 [!UICONTROL 多変量分析テスト] (MVT) および [!UICONTROL Recommendations] アクティビティ。
>
>* 消費可能 [!UICONTROL コンテンツフラグメント] in [!DNL Target] アクティビティ [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみ。 消費できません [!UICONTROL コンテンツフラグメント] の使用 [!UICONTROL Visual Experience Composer] (VEC) を参照してください。


AEMの詳細を確認するには [!UICONTROL コンテンツフラグメント] および [!UICONTROL エクスペリエンスフラグメント]を参照してください。 [AEM [!UICONTROL エクスペリエンスフラグメント] および [!UICONTROL コンテンツフラグメント] 概要](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

## 要件 {#requirements}

をプロビジョニングする必要があります。 [!UICONTROL コンテンツフラグメント] の機能 [!DNL Target]. また、 [!DNL AEM] as a Cloud Service。 アカウント担当者が、この機能を利用するための条件を満たすお手伝いをいたします。

統合の有効化と認証の詳細情報については、[Adobe Target カスタマーケア](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C)にお問い合わせください。

## の設定と操作 [!UICONTROL コンテンツフラグメント] in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

書き出す [!UICONTROL コンテンツフラグメント] 使用する [!DNL Target] アクティビティの場合は、AEMで事前の手順を実行する必要があります。 詳しくは、 [コンテンツフラグメントのAdobe Targetへの書き出し](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/integrations/content-fragments-target.html){target=_blank} 内 *Experience Manageras a Cloud Service文書*. このリンクは、リリース日（2023 年 4 月 7 日）に利用可能になります。

デザイン、作成、キュレーション、公開について詳しくは、 [!UICONTROL コンテンツフラグメント]を参照してください。 [[!UICONTROL コンテンツフラグメント]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/authoring/fundamentals/content-fragments.html?lang=en){target=_blank} and [Working with Content Fragments](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/sites/administering/content-fragments/content-fragments.html){target=_blank} in the [Experience Manager as a Cloud Service documentation](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/home.html){target=_blank}.

## 使用 [!UICONTROL コンテンツフラグメント] in [!DNL Target] アクティビティ {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

前のタスクを実行した後、 [!UICONTROL コンテンツフラグメント] が [!UICONTROL オファー] ページ内 [!DNL Target].

[!DNL Target] は現在 [!UICONTROL コンテンツフラグメント] を 10 分ごとにインポートします。 読み込まれた [!UICONTROL コンテンツフラグメント] は、 [!DNL Target] 10 分以内に、しかし、今後はこの時間枠が短くなるはずです。

この [!UICONTROL コンテンツフラグメント] 次にインポート： [!DNL Target] を JSON オファーとして設定する必要があります。 その [!UICONTROL コンテンツフラグメント] 「プライマリ」バージョンは [!DNL AEM]. 次の項目は編集できません： [!UICONTROL コンテンツフラグメント] in [!DNL Target].

フィルターおよび検索条件は、 [!UICONTROL HTMLXF], [!UICONTROL JSON XFs]、および [!UICONTROL コンテンツフラグメント] を使用して、に書き出される様々なオファータイプを区別できます。 [!DNL Target].

![コンテンツフラグメントタイプでフィルター：Target UI でのHTMLまたは JSON](/help/main/c-integrating-target-with-mac/aem/assets/fragment-types.png)

次の項目にマウスポインターを置くと、 [!UICONTROL コンテンツフラグメント] リストで、 [!UICONTROL 表示] アイコン ![情報アイコン](/help/main/c-integrating-target-with-mac/aem/assets/icon-info.png) 詳しい情報を見るには [!UICONTROL コンテンツフラグメント]( [!UICONTROL AEM path] および [!UICONTROL AEMディープリンク]. 次をクリック： [!UICONTROL オファーの使用状況] タブをクリックして、このオファーを参照するアクティビティを表示します。

![コンテンツフラグメント情報ポップアップ](/help/main/c-integrating-target-with-mac/aem/assets/cf-info-popup.png)

消費可能 [!UICONTROL コンテンツフラグメント] in [!DNL Target] アクティビティ [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md) のみ。 あなた *できません* 消費 [!UICONTROL コンテンツフラグメント] in [!DNL Target] アクティビティ [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) を参照してください。 [!UICONTROL コンテンツフラグメント] は、 [!DNL Target] とは、VEC を使用して作成されたアクティビティでは使用できません。

>[!TIP]
>
>人工知能、機械学習、および推奨事項を [!UICONTROL コンテンツフラグメント]:
>
>* を完全に使用するには [!DNL Target] AI および ML 機能では、 [自動配分](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) または [自動ターゲット](/help/main/c-activities/auto-target/auto-target-to-optimize.md) をクリックします。
>
>* [!UICONTROL コンテンツフラグメント] は、 [!DNL Recommendations] アクティビティ。 ただし、 [!UICONTROL コンテンツフラグメント] レコメンデーションの場合は、 [!UICONTROL A/B テスト] アクティビティ ( [!UICONTROL 自動配分] および [!UICONTROL 自動ターゲット]) または [!UICONTROL エクスペリエンスのターゲット設定] (XT) アクティビティと [レコメンデーションをオファーとして含める](/help/main/c-recommendations/recommendations-as-an-offer.md).


**消費する [!UICONTROL コンテンツフラグメント] の使用 [!UICONTROL フォームベースの Experience Composer]:**

1. In [!DNL Target]( [フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E)、ページ上で挿入する場所を選択します。 [!DNL AEM] コンテンツを選択し、 **[!UICONTROL コンテンツフラグメントを変更]** 表示する [!UICONTROL コンテンツフラグメントを選択] リスト。

   ![content_fragment_list 画像](/help/main/c-integrating-target-with-mac/aem/assets/choose-content-fragment.png)

   この [!UICONTROL コンテンツフラグメント] リストには、 [!DNL AEM] 現在は、内からネイティブで利用可能です。 [!DNL Target].

1. 目的のを選択します。 [!UICONTROL コンテンツフラグメント]を選択し、「 **[!UICONTROL 保存]**.
1. アクティビティの設定を終了します。

## 注意点 {#considerations}

* [!DNL Target] は現在 [!UICONTROL コンテンツフラグメント] を 10 分ごとにインポートします。 読み込まれた [!UICONTROL コンテンツフラグメント] は、 [!DNL Target] 10 分以内に、しかし、今後はこの時間枠が短くなるはずです。
* この [!UICONTROL コンテンツフラグメント] 次にインポート： [!DNL Target] を JSON オファーとして設定する必要があります。 この [!UICONTROL コンテンツフラグメント] 「プライマリ」バージョンは [!DNL AEM]. 次の項目は編集できません： [!UICONTROL コンテンツフラグメント] in [!DNL Target].
* 次を作成することはできません： [!UICONTROL コンテンツフラグメント] using [!DNL Adobe I/O]. 作成 [!UICONTROL コンテンツフラグメント] 上述のように、AEMを使用します。
* 次の場合、 [!UICONTROL コンテンツフラグメント] AEM [!UICONTROL コンテンツフラグメント] は、公開され、に書き出される必要があります [!DNL Target] 再び [!DNL Target] では、最新の変更を使用できます。