---
keywords: クリック追跡;クリックの追跡;クリック;AppMeasurement
description: ' [!DNL Adobe Target]  を使用して任意の要素に対するクリックを成功指標として追跡する方法を説明します。'
title: クリックの追跡とは
feature: Success Metrics
exl-id: 9181424b-179e-49fc-b760-b764a0c3458a
source-git-commit: 43d2484e57b1e2d292cf65c041fb9f5f49b2084c
workflow-type: tm+mt
source-wordcount: '858'
ht-degree: 75%

---

# クリックの追跡

[!DNL Adobe Target] では、任意の要素に対するクリックを成功指標として追跡できます。 クリックの追跡とは、web ページまたはエクスペリエンス内の要素に対するユーザーのインタラクション、特にクリックを監視および記録するプロセスを指します。 これは、A/B テスト、多変量分析テスト、パーソナライゼーションアクティビティでのエンゲージメントとパフォーマンスの測定における重要な部分です。

>[!NOTE]
>
>クリックの追跡は、グローバル [!DNL Target] リクエストがフォームベースのアクティビティの場所として使用される場合はサポートされません。

## クリックの追跡のセットアップ {#section_5540C5A533114E57BAE022A600B02E72}

1. アクティビティの [!UICONTROL Goals & Settings] ページで目標を設定する際に、**[!UICONTROL Conversion]** の成功指標を選択します。
1. アクションの場合は、「**[!UICONTROL Clicked an element]**」を選択し、「**[!UICONTROL Select elements]**」をクリックします。

   [!UICONTROL Visual Experience Composer] （VEC）にページが開きます。

1. 追跡する要素を選択します。

   要素の選択に関するヒントについては、次の「*注意点*」の節を参照してください。

1. 画面上部にある「**[!UICONTROL Done]**」をクリックして、選択を保存します。

選択した要素をアクティビティ参加者がクリックすると、そのクリックはコンバージョンとしてカウントされます。

## 選択された要素パネル {#selected-elements}

[!UICONTROL A/B Test]、[!UICONTROL Experience Targeting] （XT）、[!UICONTROL Automated Personalization] （AP）および [!UICONTROL Multivariate Test] （MVT）アクティビティの場合、左側のクリックの追跡用に選択された要素が [!UICONTROL Selected Elements] パネルにリストされます。

![選択された要素パネル](/help/main/c-activities/r-success-metrics/assets/selected-elements.png)

[!UICONTROL Tracked Components] ントロールパネルで要素をクリックすると、いくつかのアクションを適用できます。 以下の表で、要素で実行できる各操作を説明します。

| アクション | 説明 |
| --- | --- |
| [!UICONTROL Tracked actions] | 要素アクションを表示します。 |
| [!UICONTROL CSS selector] | CSS セクターを編集できます。 |
| [!DNL Delete] | 要素を削除します。 |

### 要素を追加

セレクターへの DOM パスが既にわかっている場合は、パネルの上部にある [!UICONTROL Add Component] アイコンをクリックして、手動で追加できます。

## 注意点 {#considerations}

要素の選択時にいくつか検討すべき事項があります。

* DOM パス機能は、クリックの追跡を設定するときに使用できます。ページで要素をクリックすると、VEC オプションメニューが表示されます。また、対応する DOM パスがページの下部に表示されます。DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

  アクティビティ作成ワークフローのステップ 1 でエクスペリエンスを作成するときと同様に、ページ下部の DOM パスセレクターで要素を選択できます。DOM パスから要素を選択すると、VEC 内の対応する要素が「選択済み」と表示されます。選択した要素の選択を解除するには、DOM パスセレクターの要素を再度クリックするか、VEC 内の「選択済み」ボックスをクリックします。

  詳しくは、*Visual Experience Composer のオプション*&#x200B;の [DOM パスを使用した要素のナビゲート](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path)を参照してください。

* 異なるページを参照して、コンテンツを変更しないページのクリックを追跡できます。[&#x200B; 複数ページ機能 &#x200B;](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) を使用して、この異なるページをアクティビティに含め、[!DNL at.js] れを実装する必要があります。
* 1 つ以上の要素を選択した場合、参加者が選択した要素のいずれかをクリックすると、クリックがカウントされます。各項目を個別にカウントする場合、要素ごとに個別の成功指標を設定します。ページ上の複数の要素をクリックして 1 つの項目をカウントするには、CSS 要素セレクターを編集して複数の要素と一致させます。
* 追跡する要素のレベルを選択していることを確認してください。例えば、ボタンを指定する場合、ボタンテキストでなくリンクを選択していることを確認します。
* クリックイベントは、そのクリックと同じページの [!DNL Target] に送信されます。
* クリック追跡指標が [!UICONTROL Analytics for Target] （A4T）アクティビティの目標指標の場合は、訪問者がページの読み込みから 60 秒以内にこの要素をクリックしないと、指標は追跡されません。
* 次に示すエスケープ文字がセレクターに含まれる要素では、クリックの追跡は機能しません。

  | 文字 | 説明 |
  |---|---|
  | # | 番号記号またはハッシュ |
  | : | コロン |
  | 。 | ピリオド |
  | $ | ドル記号 |
  | `[ ]` | 角括弧 |

* [!DNL at.js] のクリック追跡に加えて [!DNL Analytics] AppMeasurement も使用した場合、[!DNL at.js] のクリック追跡によって他のすべてのクリックイベントハンドラーがキャンセルされます。その結果、AppMeasurement のクリックハンドラーは実行されなくなります。

  [!DNL at.js] では、基になる要素が `A`（リンク）タグまたは `FORM` タグの場合にクリックの追跡のための特別な処理が実行されます。

  クリックの追跡イベントが [!DNL at.js]（リンク）タグまたは `A` タグに付加されている場合、次の手順が `FORM` によって実行されます。

   1. `event.preventDefault()` を呼び出す。

   1. [!DNL Target] リクエストをトリガーします。

   1. [!DNL Target] リクエストの成功またはエラーコールバックで、デフォルトの動作を実行します。

      * `A`（リンク）タグ：デフォルトの動作では、HREF 属性に定義されている URL に移動します。
      * `FORM` タグ：デフォルトの動作では、フォームを送信します。

  このデフォルトの動作により、[!DNL Analytics] のクリックの追跡が妨げられることがあります。[!DNL Analytics] を使用している場合は、[!DNL Target] ではなく [!DNL Analytics] を使用してクリックの追跡を行う必要があります。

* クリックの追跡は、ページおよびアクティビティ URL が異なるプロパティに属しているページには記録されません。エンタープライズユーザー権限は [!DNL Target Premium] の機能です。詳しくは、[Enterprise ユーザー権限](/help/main/administrating-target/c-user-management/property-channel/property-channel.md)を参照してください。

* クリック追跡指標は、アクティビティの特定のエクスペリエンスにはリンクされません。

* クリック追跡指標の範囲を制限する必要がある場合は、オーディエンスを使用します。

* 複数のアクティビティで、同じセレクターのクリック追跡指標を定義できます。その場合、訪問者がそのアクティビティの 1 つに該当し、そのセレクターをクリックすると、クリック追跡指標は、その訪問者が該当するすべての関連アクティビティについて増加します。

## トレーニングビデオ {#section_36607204DAE146E3B8E2C609D244EDB1}

このビデオでは、クリックの追跡の成功指標の作成について説明します。

* 「目標」指標の理解
* [!UICONTROL Conversion]、[!UICONTROL Revenue]、[!UICONTROL Engagement] の指標の理解と作成
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380)
