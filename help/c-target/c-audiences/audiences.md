---
keywords: オーディエンス、オーディエンスルール、オーディエンスの作成、オーディエンスの作成、ターゲットオーディエンス、レポートオーディエンス、レポートオーディエンス、セグメント、カスタムプロファイルパラメーター、オーディエンス定義、オーディエンスリスト
description: Adobe [!DNL Target] の[!UICONTROL オーディエンス]リストの使用方法と、オーディエンスの詳細および使用状況情報を含むオーディエンス定義カードの表示方法について説明します。
title: オーディエンスリストの使用方法
feature: オーディエンス
exl-id: 7af7f101-f550-4fdc-bcd9-90e4107b0415
source-git-commit: 06a5fda72a649c4037cb78d3e670747cd297a64d
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 58%

---

# オーディエンスの作成

[!DNL Adobe Target]のオーディエンスは、誰がターゲットアクティビティでコンテンツやエクスペリエンスを表示するかを決定します。

オーディエンスは、ターゲット設定を利用できるあらゆる場所で使用されます。アクティビティをターゲティングする際には、次のオプションを使用できます。

* [!UICONTROL オーディエンス]リストから再利用可能なオーディエンスを選択します
* [アクティビティ固有のオーディエンスを作](/help/c-target/creating-activity-only-audience.md) 成し、ターゲットに設定する
* [複数のオーディエ](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) ンスを組み合わせてアドホックオーディエンスを作成する

[!DNL Adobe Analytics]で収集されたオーディエンスデータは、[!DNL Target]や他の[!DNL Adobe Experience Cloud]アプリケーションでのリアルタイムのターゲティングやパーソナライゼーションにも使用できます。 『*Experience Cloud中央インターフェイスコンポーネント*』ガイドの「[Experience Cloudオーディエンス](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=ja)」を参照してください。

[!DNL Target] では、次の 2 種類のオーディエンスが定義されます。

* **ターゲット設定するオーディエンス：**&#x200B;異なる種類の訪問者に異なるコンテンツを配信するために使用します。
* **レポート用オーディエンス：**&#x200B;同じコンテンツに異なる種類の訪問者がどのように反応するかを判断し、テスト結果を分析するために使用します。

   [!DNL Target] では、レポートソースとして [!DNL Target] を使用する場合にのみ、レポート用オーディエンスを設定できます。レポートソースとして [ Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md)（A4T）を使用する場合は、[!DNL Analytics] 内でレポート用オーディエンスを設定する必要があります。

## [!UICONTROL オーディエンス]リストを使用します

[!UICONTROL オーディエンス]リストにアクセスするには、上部のメニューバーで「**[!UICONTROL オーディエンス]**」をクリックします。

![オーディエンスリスト](/help/c-target/c-audiences/assets/audiences_list.png)

[!UICONTROL オーディエンス]リストには、アクティビティで使用できるすべてのオーディエンスが含まれています。[!UICONTROL オーディエンス]リストを使用して、オーディエンスの作成、編集、削除、コピー、組み合わせが可能です。また、オーディエンスが作成されたソース([!DNL Target]、[!DNL Target Classic]、[!DNL Experience Cloud])も表示されます。 「[!UICONTROL 新しい訪問者]」や「[!UICONTROL 再訪問者]」などの事前定義されたオーディエンスは、名前を変更できません。

最初に[!DNL Experience Cloud]で作成されたオーディエンスを操作する際に、後で[!DNL Experience Cloud]で削除された[!DNL Target]アクティビティでオーディエンスを参照すると、Targetは警告を表示します。

* [!DNL Experience Cloud]でオーディエンスが削除された場合、[!UICONTROL Audience]リストとオーディエンスピッカーの両方に警告アイコンが表示されます。 UIのツールチップも、オーディエンスが[!DNL Experience Cloud]で削除されたことを示します。
* 複数のオーディエンスを削除済みのオーディエンスに結合しようとした場合、または削除済みのオーディエンスを参照しているアクティビティを保存しようとした場合、警告メッセージが表示されます。

カスタムプロファイルパラメーターおよび `user.` パラメーターをターゲット設定することもできます。オーディエンスを追加する場合、アクティビティのターゲット設定に使用する属性をクリックします。 目的の属性が表示されない場合、その属性はmboxで実行されていません。 他のカスタム mbox パラメーターは、[!UICONTROL カスタムパラメーター]ドロップダウンリストに表示されます。

「[!UICONTROL フィルター]」ボタンを使用して、ソースを基準に[!UICONTROL オーディエンス]リストをフィルタリングします。[!DNL Adobe Target]、[!DNL Adobe Target Classic]、および[!DNL Experience Cloud]。

![オーディエンスリストの「フィルター」オプ  ション](/help/c-target/c-audiences/assets/filters.png)

「[!UICONTROL オーディエンスを検索]」ボックスを使用して、[!UICONTROL オーディエンス]リストを検索します。 オーディエンス名の一部で検索したり、特定の文字列を引用符で囲んだりすることも可能です。

[!UICONTROL オーディエンス]リストは、オーディエンス名または最終更新日付で並べ替えることができます。名前や日付で並べ替える場合は、列見出しをクリックし、昇順または降順でオーディエンスを表示するよう選択します。

## オーディエンス定義を表示 {#section_11B9C4A777E14D36BA1E925021945780}

オーディエンス定義の詳細は、オーディエンスを開かなくても、Target UI の様々な場所に表示されるポップアップカードで確認できます。この機能は、[!DNL Target Standard/Premium]で作成されたオーディエンスと[!DNL Target Classic]からインポートされたオーディエンス、またはAPIを介して作成されたオーディエンスに適用されます。

例えば、次のオーディエンス定義カードは、目的のオーディエンスの[!UICONTROL 詳細を表示]アイコンをクリックすると表示されます。

![アクティビティ／オーディエンス定義](assets/audience_definition_list.png)

次のオーディエンス定義カードにアクセスするには、アクティビティの[!UICONTROL 概要]ページにある[!UICONTROL 詳細を表示]アイコンをクリックします。

![アクティビティ／オーディエンス定義](/help/c-target/c-audiences/assets/view-details-activity-overview.png)

オーディエンス定義カードには、オーディエンスのタイプ、ソースおよび属性が表示されます。 該当する場合は、「**[!UICONTROL 詳細を表示]**」をクリックして、そのオーディエンスを参照する他のアクティビティを表示します。 アクティビティの[!UICONTROL 概要]ページからオーディエンス定義カードを表示している場合は、「**[!UICONTROL オーディエンスの使用]**」をクリックします。

オーディエンスの使用状況に関する情報は、オーディエンスの編集中に他のアクティビティに予期しない影響が及ぶのを防ぐのに役立ちます。 ライブアクティビティ、非アクティブなアクティビティ、アーカイブ済みアクティビティ、同期中のアクティビティなどの情報を参照できます。この機能は、すべてのオーディエンス（ライブラリオーディエンスおよび[アクティビティのみのオーディエンス](/help/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483)）で利用できます。

オーディエンスが別のオーディエンスと結合され、結合オーディエンスがアクティビティの作成に使用された場合、両方のオーディエンスの使用状況情報には、新しく作成されたアクティビティが表示されます。

![](assets/audience_definition_list_usage.png)

次のオーディエンス定義カードは、Adobe Experience Cloud からインポートしたオーディエンスのものです。この例では、オーディエンスは Adobe Audience Manager（AAM）からインポートされています。

![オーディエンス定義カード上のタブの使用](assets/audience_definition_mc.png)

インポートしたオーディエンスのタイプごとに確認できる詳細情報は次のとおりです。

| オーディエンスのタイプ | 詳細 |
|--- |--- |
| モバイルオーディエンス | マーケティング名、ベンダー、モデル。<br>「 `matches | does not match` インポートされた `equals | does not equal`<br>![モバイルオーディエンス」の代わりに演算子が表示されます](/help/c-target/c-audiences/assets/imported_mobile_audience.png)。 |
| 訪問者の行動オーディエンス | **user. categoryAffinity:** `categoryAffinity` `FAVORITE` パラメーターを使用します。<br>![インポートされたカテゴリーの親和性監視&#x200B;](/help/c-target/c-audiences/assets/imported_category_affinity.png)<br>**:** 監視サービスがtrueに等しい。<br>**監視なし：** Monitoring service equals false.<br>![インポートされた監視](/help/c-target/c-audiences/assets/imported_monitoring.png) |
| NOT 演算子を使用するオーディエンス | **単一ルール:** Targetはオーディエンスを形式で表示 `[All Visitor AND [NOT [rule]` します。単一のNOTルールは、ANDと共に `AllVisitor` 表示されます。<br>![インポートされないオーディエンス](/help/c-target/c-audiences/assets/imported_not_audience.png) |

インポートしたオーディエンスを操作する際は、次の点に注意してください。

* Target Standard／Premium では、エクスプレッションターゲットオーディエンスはサポートされなくなりました。
* Target Standard／Premium では、非推奨のオーディエンスをサポートしていない場合や、使いやすいように演算子が改良されている場合があります。そのため、インポートしたオーディエンスの定義は、定義どおりに機能しますが、Standard／Premium インターフェイスで同じものを作成することはできない場合があります。例えば、ソーシャルオーディエンスはルールとともに表示されますが、Target Standard／Premium で作成することはできません。

## トレーニングビデオ: Audiencesの使用![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、オーディエンスの使用に関する情報が説明されています。

* 用語「オーディエンス」の説明
* 最適化のためにオーディエンスを使用する 2 つの方法の説明
* オーディエンスリストでのオーディエンスの検索
* アクティビティのオーディエンスへのターゲット設定
* アクティビティの受動的なレポート用でのオーディエンスの使用

>[!VIDEO](https://video.tv.adobe.com/v/17398)
