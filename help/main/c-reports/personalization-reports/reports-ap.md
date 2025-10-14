---
keywords: ターゲティング；AP レポート；Automated Personalization レポート；アクティビティレベル レポート；オファーレベル レポート；オファー詳細レポート；FAQ
description: Adobe TargetでAutomated Personalization概要レポートを解釈する方法について説明します。 このレポートから自動セグメント レポートと重要な属性レポートに切り替えることができます。
title: Automated Personalization概要レポートの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 13%

---

# Automated Personalization 概要レポート

[!UICONTROL Automated Personalization] の [!DNL Adobe Target] のアクティビティのユーザーは、専用の概要レポートを使用できます。

>[!NOTE]
>
>[!UICONTROL Automated Personalization] は、[!DNL Target Premium] ソリューションの一部として利用できます。 [!DNL Target Standard]Target Premium ライセンス [&#x200B; のない &#x200B;](/help/main/c-intro/intro.md#premium) には含まれていません。

1. 「**[!UICONTROL Activities]**」をクリックし、リストから目的の [!UICONTROL Automated Personalization] アクティビティをクリックして、「**[!UICONTROL Reports]**」タブをクリックします。

   アクティビティが多数ある場合は、フィルター（![&#x200B; フィルターアイコン &#x200B;](/help/main/assets/icons/Filter.svg)）アイコンをクリックし、「[!UICONTROL Type]」、「[!UICONTROL Status]」、「[!UICONTROL Reporting Source]」、「[!UICONTROL Experience Composer]」、「[!UICONTROL Metrics Type]」、「[!UICONTROL Activity Source]」の各ドロップダウンリストからオプションを選択してリストをフィルタリングします。

1. （任意） **[!UICONTROL Download]** （![&#x200B; ダウンロードアイコン &#x200B;](/help/main/assets/icons/Download.svg)）アイコンをクリックして、使用可能なすべての成功指標に分類された概要ビュー（例えば、コントロールトラフィックとターゲットトラフィックの比較）をダウンロードします。

[!UICONTROL Automated Personalization] は次のレポートを提供します。

* アクティビティレベル
* オファーレベル
* 自動セグメント
* 重要な属性

## アクティビティレベルレポート {#section_6F72FC5C790B4492B3DCECBFFA971337}

[!UICONTROL Activity Level] レポートでは、[!UICONTROL Automated Personalization] アルゴリズムを使用しての集計パフォーマンスを、ランダムに提供されるコンテンツ（コントロール）と比較します。

上昇率、信頼性、トレンド、期間などを含む、A/B テストの結果を解釈する標準ルールは、依然として適用されます。結果の解釈について詳しくは、[A/Bn テストでの統計計算 &#x200B;](/help/main/c-reports/statistical-methodology/statistical-calculations.md) を参照してください。

## オファーレベルレポート {#section_CAA6409879E349C6906E2BE8156D87A1}

ランダムフォレストエクスペリエンスの [!UICONTROL Offer Level] レポートでは、アルゴリズムが適用された各オファーのパフォーマンスを、ランダムに提供される同じオファー（コントロール）と比較します。 したがって、このビューでは、オファーを相互に比較しないでください。

エクスペリエンスアルゴリズム（ランダムフォレストまたはコントロール）をクリックして、[!UICONTROL Offer Level] レポートを表示します。

>[!NOTE]
>
>時計アイコンは、アルゴリズムモデルがまだ作成中であることを示します。 チェックマークアイコンは、ベースアルゴリズムが確立されたことを示します。

オファーは [&#x200B; レポートグループ &#x200B;](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md) 内に表示することができ、これらのレポートグループは折りたたんだり展開したりできます。 テーブルで **[!UICONTROL Control]** または **[!UICONTROL Targeted]** をクリックすると、オファーごとではなくレポートグループごとにロールアップされた情報が表示されます。

## 自動セグメント

[!UICONTROL Automated Segments] アイコンをクリックします。 このレポートは、AP/AT アクティビティのオファー/エクスペリエンスに対する様々な訪問者の反応を示します。 このレポートは、Target のパーソナライゼーションモデルで定義された様々な自動セグメントがアクティビティのオファー／エクスペリエンスにどう反応しているかを示します。

詳しくは、[&#x200B; 自動セグメントレポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) を参照してください。

## 重要な属性

[!UICONTROL Important Attributes] アイコンをクリックします。 このレポートでは、モデルがどのようにパーソナライズを決定するかについて、様々なアクティビティで様々な属性がより多く（または少なく）重要である様子を示します。 このレポートは、モデルに影響を及ぼした上位の属性とそれら属性の相対的重要性を示します。

詳しくは、[&#x200B; 重要な属性レポート &#x200B;](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) を参照してください。

## よくある質問

### アクティビティレベルとオファーレベルのレポートでデータに違いがあるのはなぜですか？

**[!UICONTROL Activity Level]レポート**:[!UICONTROL Activity Level] レポートに記録される訪問は、「ターゲット」トラフィックと比較して、コントロールエクスペリエンスの訪問回数をキャプチャします。 ターゲットトラフィックには、探索トラフィックとパーソナライズされたトラフィックの組み合わせが含まれます。

**オファーレベルのレポート**:[!UICONTROL Offer Level] レポートに記録されるインプレッション数は、各オファーのインプレッション数を示します。 したがって、複数の場所を使用するアクティビティの場合、すべてのレポートグループの [!UICONTROL Offer Level] レポートに記録される訪問総数は、[!UICONTROL Activity Level] レポートのコントロールトラフィックまたはターゲットトラフィックに記録される訪問数の倍数と、アクティビティの場所の合計数を乗算した数と等しくなります。 デフォルトコンテンツが使用可能な場所にあった場合、その場所で発生したデフォルトコンテンツのインプレッションは、「デフォルトコンテンツ」オファーグループに記録されます。 レポートグループに割り当てられていないオファーのインプレッションは、「グループ解除」オファーグループに記録されます。

>[!NOTE]
>
>[!UICONTROL Offer Level] レポートに記録されるインプレッション数は、[!UICONTROL Activity Level] レポートに記録される訪問数の正確な整数倍でない場合があります。 これは、インターネットを介したレポートデータトラフィックのキャプチャで発生する小さな不一致に起因します（通常の不一致レートは 5% 未満）。 したがって、アクティビティがアクティブ化された後に、アクティビティで使用可能な場所の数が変更された場合、インプレッションの数は正確な倍数になりません。
