---
description: Target では、任意の要素に対するクリックを成功指標として追跡できます。
keywords: クリック追跡;クリックの追跡;クリック;AppMeasurement
seo-description: Target では、任意の要素に対するクリックを成功指標として追跡できます。
seo-title: クリックの追跡
solution: 'Target '
subtopic: 導入
title: クリックの追跡
topic: Standard
uuid: 4a8fbb23-93d8-49f3-aca3-dbbdd6da0178
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# クリックの追跡{#click-tracking}

Target では、任意の要素に対するクリックを成功指標として追跡できます。

>[!NOTE]
>
>クリックの追跡は、ターゲットグローバル mbox がフォームベースのアクティビティの場所として使用されている場合はサポートされません。

## Setting Up click tracking {#section_5540C5A533114E57BAE022A600B02E72}

1. アクティビティの[!UICONTROL 目標と設定]ページで目標を設定する際に、**[!UICONTROL コンバージョン]**&#x200B;成功指標を選択します。
1. アクションの場合、「**[!UICONTROL 要素をクリック]**」を選択し、「**[!UICONTROL 要素を選択**]」をクリックします。

   [!UICONTROL Visual Experience Composer]（VEC）でページが開きます。

1. 追跡する要素を選択します。

   要素の選択に関するヒントについては、次の「注意点」の節を参照してください。

1. 画面上部にあるチェックマークをクリックして、選択を保存します。

選択した要素をアクティビティ参加者がクリックすると、そのクリックはコンバージョンとしてカウントされます。

## Selected Elements panel {#selected-elements}

For A/B Test, Experience Targeting (XT), Automated Personalization (AP), and Multivariate Test (MVT) activities, a [!UICONTROL Selected Elements] panel lists all of the selected elements for click tracking on the right side.

![選択したエレメントパネル](/help/c-activities/r-success-metrics/assets/selected-elements.png)

There are a several actions that can be applied when you hover over an element in the [!UICONTROL Selected Elements] panel. 次の表で、要素に対して実行できる各アクションについて説明します。

| アクション | 説明 |
| --- | --- |
| 情報 | 要素タイプと、セレクターへのフルDOMパスを表示します。 |
| 編集 | CSSセレクターを編集できます。 |
| 削除 | 要素を削除します。 |

### 要素の追加

セレクターのDOMパスが既にわかっている場合は、パネルの上部にあるプラスアイコンをクリックして手動で追加できます。

![要素を追加アイコン](/help/c-activities/r-success-metrics/assets/add-element.png)

### 選択したエレメントカーソルポップアップ

After selecting multiple elements for click tracking, you can click the [!UICONTROL Elements Selected] link on the activity's [!UICONTROL Goals &amp; Settings] step to see the full list of elements selected for click tracking. このリストには、選択した要素がクリック追跡に使用されることを検証するために、要素の完全なDOMパスが含まれています。

![エレメント選択リンク](/help/c-activities/r-success-metrics/assets/elements-selected-link.png)

## 注意点 {#considerations}

要素の選択時にいくつか検討すべき事項があります。

* DOM パス機能は、クリックの追跡を設定するときに使用できます。ページで要素をクリックすると、VEC オプションメニューが表示されます。また、対応する DOM パスがページの下部に表示されます。DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

   ![DOM パスの解説](/help/c-activities/r-success-metrics/assets/click-tracking-dom.png)

   アクティビティ作成ワークフローの手順1でエクスペリエンスを作成するときと同様に、ページ下部の DOM パスセレクターで要素を選択できます。DOM パスから要素を選択すると、VEC 内の対応する要素が「選択済み」と表示されます。選択した要素の選択を解除するには、DOM パスセレクターの要素を再度クリックするか、VEC 内の「選択済み」ボックスをクリックします。

   詳しくは、Visual Experience Composer のオプション](/help/c-experiences/c-visual-experience-composer/viztarget-options.md#dom-path) の *[「DOM パスを使用して要素をナビゲートする」を*&#x200B;参照してください。

* 異なるページを参照して、コンテンツを変更しないページのクリックを追跡できます。この異なるページは、[複数ページ機能](../../c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48) を使用するアクティビティに含める必要があり、[!DNL at.js] または [!DNL mbox.js] を実装する必要があります。
* 1 つ以上の要素を選択した場合、参加者が選択した要素のいずれかをクリックすると、クリックがカウントされます。各項目を個別にカウントする場合、要素ごとに個別の成功指標を設定します。
* 追跡する要素のレベルを選択していることを確認してください。例えば、ボタンを指定する場合、ボタンテキストでなくリンクを選択していることを確認します。
* クリックイベントは、そのクリックと同じページの [!DNL Target] に送信されます。
* クリック追跡指標が A4T アクティビティの目標指標の場合は、訪問者がページの読み込みから 60 秒以内にこの要素をクリックしないと、指標は追跡されません。
* 次に示すエスケープ文字がセレクターに含まれる要素では、クリックの追跡は機能しません。

   | 文字 | 説明 |
   |---|---|
   | # | 番号記号またはハッシュ |
   | : | コロン |
   | を参照してください。 | ピリオド |
   | $ | ドル記号 |
   | `[ ]` | 角括弧 |

* [!DNL at.js] のクリックの追跡に加えて Analytics AppMeasurement も使用した場合、[!DNL at.js] のクリックの追跡によって他のすべてのクリックイベントハンドラーがキャンセルされます。その結果、AppMeasurement のクリックハンドラーは実行されなくなります。

   [!DNL at.js] では、基になる要素が `A`（リンク）タグまたは `FORM` タグの場合にクリックの追跡のための特別な処理が実行されます。

   クリックの追跡イベントが [!DNL at.js]（リンク）タグまたは `A` タグに付加されている場合、次の手順が `FORM` によって実行されます。

   1. `event.preventDefault()` を呼び出す。

   1. Target リクエストを発行します。

   1. Target リクエストの成功またはエラーコールバックで、デフォルトの動作を実行します。

      * `A`（リンク）タグ：デフォルトの動作では、HREF 属性に定義されている URL に移動します。
      * `FORM` タグ：デフォルトの動作では、フォームを送信します。
   このデフォルトの動作により、Analytics のクリックの追跡が妨げられることがあります。Analytics を使用している場合は、Target ではなく Analytics を使用してクリックの追跡をおこなう必要があります。

* クリックの追跡は、ページおよびアクティビティ URL が異なるプロパティに属しているページには記録されません。Enterprise ユーザー権限は Target Premium 機能です。詳しくは 、[Enterprise ユーザー権限](/help/administrating-target/c-user-management/property-channel/property-channel.md)を参照してください。

## トレーニングビデオ {#section_36607204DAE146E3B8E2C609D244EDB1}

このビデオでは、クリックの追跡の成功指標の作成について説明します。

* 「目標」指標の理解
* コンバージョン、収益、エンゲージメントの指標の理解と構築
* クリック追跡指標の構築

>[!VIDEO](https://video.tv.adobe.com/v/17380?captions=jpn)