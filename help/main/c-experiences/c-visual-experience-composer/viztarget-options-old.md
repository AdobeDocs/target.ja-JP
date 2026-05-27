---
keywords: visual experience composer オプション；experience options;experience options;edit text;edit html;edit text/html;edit background color;insert element;edit link;visual experience composer link;edit css class;css class;swap offer;offer swap image;image swap;remove item;remove item;item;hide item;hide item;rearrange;move element;move;element move;element resize;element;resize;element;expand selection;navigate;link;navigate;undo;redo；元に戻す/やり直し；カスタム イベントのオファーwebの決定決定
description: ' [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）で使用可能なオプションを確認します。'
title: '[!UICONTROL Visual Experience Composer] （VEC） オプションの使用方法を教えてください。'
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2804'
ht-degree: 55%

---

# Visual Experience Composer のオプション

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）のページ要素をクリックすると、その要素タイプで使用できるオプションがメニューに表示されます。 さらに、ページの下部に DOM パスが表示されるので、ページ構造を簡単にナビゲートできます。

様々な[!UICONTROL Visual Experience Composer] （VEC） アクションは、ジョブをより迅速かつ効率的にするために、適切なメニューオプションにグループ化されます。

![VEC オプションメニュー](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>使用可能なオプションは、作成または編集するアクティビティタイプによって異なります。

## [!UICONTROL Edit]

以下のオプションがあります。

### [!UICONTROL Text/HTML] {#edit-text-html}

要素の HTML コード（テキスト領域、ボタン、リンクのテキストなど）を変更します。

HTML コードだけでなく、カスタム JavaScript を編集および挿入することもできます。

[!UICONTROL A/B]および[!UICONTROL Experience Targeting]のアクティビティでテキストとHTMLを編集する場合は、いくつかのリッチテキスト書式設定オプションを利用できます。 フォントの選択、フォントスタイルの選択、テキストの整列方法の変更およびその他の標準的なテキスト書式オプションの設定が可能です。 HTML を変更する際に、HTML のコードビューとリッチ編集ビューを切り替えることができます。

次の HTML5 タグをネストできます。

| タグ | ネスト可能なタグ |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

カラーピッカーを使用して、背景色を選択または設定します。 カラースウォッチを選択して、RGB 値またはカラー 16 進コードを使用して調整できます。 カラーピッカーの赤 x は、背景を透明にします。

**注意：**&#x200B;背景画像が設定されている要素に対しては、このオプションは利用できません。

### [!UICONTROL Styles] {#styles}

[!UICONTROL Styles] パネルを使用して、選択した要素の既存のスタイルの値を表示または編集します。 その他のスタイルを追加することもできます。

[!UICONTROL Styles] パネルにアクセスするには、VEC内からページ要素をクリックし、**[!UICONTROL Edit]** > **[!UICONTROL Styles]**&#x200B;をクリックします。

VECの右側に[!UICONTROL Styles] パネルが表示されます。 このパネルには、編集または選択した要素に追加できるスタイルのリストが含まれています。 リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

![スタイルパネル](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

異なるスタイルを適用する場合は、セクションを変更した後に[!UICONTROL Styles] パネルの右上隅に表示される[!UICONTROL Revert] アイコンをクリックして、いつでも変更を元に戻すことができます。 [!UICONTROL Revert] アイコンをクリックすると、現在のセクションのパネルのすべての変更が元に戻ります。

後述のように、各セクションを展開して、スタイルを編集または追加します。 変更を保存するには、パネルの上部にある[!UICONTROL Back] アイコンをクリックして、パネルのメインディスプレイに戻り、**[!UICONTROL Save]**&#x200B;をクリックします。

メインパネルの青い点と、さまざまなセクション パネルの各オプションの横にある青い点は、対応するスタイルを変更したことを示します。 この視覚的なインジケーターを使用すると、[!UICONTROL Save]をクリックする前に変更内容を簡単に確認できます。

>[!NOTE]
>
>レイアウト変更、背景色、サイズ変更、移動のクイックアクションは、VEC メニューの個別のアクションとしても使用できます。 これらのオプションは、個別のアクションとして使用することも、スタイルメニューを使用することもできます。詳しくは、こちらを参照してください。

* **[!UICONTROL Background]**

  背景色および画像を変更します。

   * 色（カラーコードを指定するか、カラーピッカーを使用）
   * 画像（イメージピッカーから画像を選択）
   * 画像ソース（外部 URL を指定）
   * 添付ファイル
      * 上部のドロップダウンリストをクリックして、スクロール、固定またはローカルを選択
      * 下部のドロップダウンリストをクリックして、繰り返し、繰り返し X、繰り返し Y、繰り返しなし、スペースまたはラウンドを選択
   * クリップ
      * 上部のドロップダウンリストをクリックして、境界線ボックス、パディングボックス、コンテンツボックスまたはテキストを選択
      * 下部のドロップダウンリストをクリックして、自動音声または音声を選択

* **[!UICONTROL Typography]**

  要素のタイポグラフィを変更します。 タイポグラフィの編集は手軽におこなえます。

  リッチテキストエディター（テキストを編集/HTML）は微調整に使用できますが、エレメント全体を変更するクイックアクションはこのオプションを使用して使用できます。 （テキスト全体ではなく）テキストの一部にのみタイポグラフィの変更を適用する場合は、[リッチテキストエディター](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)を使用します。

  次のタイポグラフィスタイルを編集できます。

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] （カラーコードを指定するか、カラーピッカーを使用してください）
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  選択した要素の余白を変更します。 左、右、下、上の余白を変更できます。

  各余白のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （スライダーをドラッグしてマージンを設定するか、各マージンのピクセル数を指定します）

  余白は正と負の値をサポートします。

  Targetは、rem、pc、emなどの他のサイズ単位もサポートしています。 これらのユニットについて詳しくは、[Web スタイルシート CSSのヒントとテクニック ](https://www.w3.org/Style/Examples/007/units.en.html)を参照してください。

* **[!UICONTROL Padding]**

  選択した要素のパディングを変更します。 左、右、下、上のパディングを変更できます。

  スライダーをドラッグしてパディングを設定するか、パディングのピクセル数を指定します。

  パディングは 0 以上の幅に対応します。

  Targetは、rem、pc、emなど、[その他のサイズ単位](https://www.w3.org/Style/Examples/007/units.en.html)もサポートしています。

* **[!UICONTROL Border]**

  パネルの上部にある境界線アイコンをクリックして、選択した要素の境界線を変更します。

  境界線ごとに（上、右、下、左）、次のスタイルを編集できます。

   * [!UICONTROL Border style] （なし、非表示、点線、破線、実線、ダブル）
   * [!UICONTROL Border color] （カラーコードを指定するか、カラーピッカーを使用してください）
   * [!UICONTROL Border width] （スライダーをドラッグして境界線の幅を選択するか、幅をピクセル単位で指定します）

  境界線は 0 以上の幅に対応します。

  Targetは、rem、pc、emなど、[その他のサイズ単位](https://www.w3.org/Style/Examples/007/units.en.html)もサポートしています。

* **[!UICONTROL Position]**

  選択した要素を現在の位置から移動します。 要素の上、下、左、右、[Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp)の位置を変更できます。

  [!UICONTROL Static] ドロップダウンリストをクリックして、次の位置オプションから選択します。

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  各位置のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （スライダーをドラッグして要素を配置するか、要素を移動するピクセル数を指定します）

  位置は正と負の値をサポートします。

  Targetは、rem、pc、emなど、[その他のサイズ単位](https://www.w3.org/Style/Examples/007/units.en.html)もサポートしています。

* **[!UICONTROL Size]**

  選択した要素の幅と高さを変更します。

  [!UICONTROL Width]と[!UICONTROL Height]の横にあるドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （スライダーをドラッグして要素のサイズを変更するか、ディメンションごとにピクセル数を指定します）

* **[!UICONTROL Filter]**

  各フィルターオプションのスライダーをドラッグするか、目的の割合（％）を指定します。

   * [!UICONTROL Sepia]
   * [!UICONTROL Contrast]
   * [!UICONTROL Brightness]
   * [!UICONTROL GrayScale]
   * [!UICONTROL Blur]
   * [!UICONTROL Opacity]
   * [!UICONTROL Invert]
*[!UICONTROL  Hue-rotate]
   * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

  CSS エディターには、スタイルパネルでおこなった変更が表示されます。 下の図では、フォントサイズ、上の境界線、画像サイズが変更されました。

  ![変更を反映した CSS エディター](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  前の図の[!UICONTROL Typography]、[!UICONTROL Border]および[!UICONTROL Size] オプションの横にある青い点に注意してください。 これらの点は、これらのセクションを変更したことを示します。 これらのセクションパネルを開くと、変更した特定のオプションの横に青いドットが表示されます。

  希望するスタイルが[!UICONTROL Styles]でデフォルトで使用できない場合は、独自のコードを入力できます。

  CSS エディターには、現在のセッションの詳細のみが表示されます。 変更を保存してエディターを再度開いた場合、同じ要素を再度選択しても、前の変更に関する詳細はエディターには表示されません。

  >[!IMPORTANT]
  >
  >CSS エディターを使用して背景画像を適用できますが、ちらつきが生じる場合があります。 デプロイする前に変更をテストしてください。

### [!UICONTROL CSS Class]

要素で使用する事前定義 CSS クラスを指定します。 複数の要素が選択されている場合は、複数の CSS クラスをスペースで区切ります。

[!UICONTROL A/B]、[!UICONTROL Automated Personalization]および[!UICONTROL Multivariate Test]のアクティビティで使用できます。

### [!UICONTROL Link]

リンクの URL を変更します。

「リンクを編集」を使用して、同じ画像要素を指定するセレクターを更新します。 ただし、異なる画像要素へのリンクはサポートされていません。 別の画像要素にリンクするには、コードエディターから元のアクションを削除し、[!UICONTROL Visual Experience Composer]を使用して他の画像要素にアクションを適用します。

## [!UICONTROL Insert Before]

以下のオプションがあります。

### [!UICONTROL Offer Decision]

 [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}で作成された[ オファーを追加して、オファー決定機能を使用して顧客に最適なオファーとエクスペリエンスを提示します。

**注意：**&#x200B;このオプションは、[手動[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)または[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティの編集または作成時にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、[ オファー決定の使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)を参照してください。

### [!UICONTROL Image]、[!UICONTROL HTML]、[!UICONTROL Text]

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。 テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページ上の要素を選択し、[!UICONTROL Insert Before]をクリックして、画像、HTML、またはテキストを挿入するかどうかを選択します。 挿入された要素は、選択した要素の前に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。 ページが正しく表示されるためには、有効な HTML を指定する必要があります。 アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations]は、DIV、SECTION、およびARTICLE タグの内容[!UICONTROL Insert Before]をサポートしています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

### レコメンデーション

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内にレコメンデーションを含めます。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。

### [!UICONTROL Experience Fragment]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。 詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL Insert After]

以下のオプションがあります。

### [!UICONTROL Offer Decision]

 [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}で作成された[ オファーを追加して、オファー決定機能を使用して顧客に最適なオファーとエクスペリエンスを提示します。

**注意：**&#x200B;このオプションは、[手動[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)または[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティの編集または作成時にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、[ オファー決定の使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)を参照してください。

### [!UICONTROL Image]、[!UICONTROL HTML]、[!UICONTROL Text]

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。 テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページ上の要素を選択し、[!UICONTROL Insert After]をクリックして、画像、HTML、またはテキストを挿入するかどうかを選択します。 挿入された要素は、選択した要素の後に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。 ページが正しく表示されるためには、有効な HTML を指定する必要があります。 アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations]は、DIV、SECTION、およびARTICLE タグの内容[!UICONTROL Insert After]をサポートしています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

### レコメンデーション

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内にレコメンデーションを含めます。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。

### [!UICONTROL Experience Fragment]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。 詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL Replace Content]

以下のオプションがあります。

### [!UICONTROL Offer Decision]

 [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank}で作成された[ オファーを追加して、オファー決定機能を使用して顧客に最適なオファーとエクスペリエンスを提示します。

**注意：**&#x200B;このオプションは、[手動[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types)または[[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティの編集または作成時にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、[ オファー決定の使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md)を参照してください。

### [!UICONTROL Image]

コンテンツライブラリから別の画像を選択します。 スワップに利用できる画像には、Experience Cloud アセットフォルダーまたは Target のコンテンツライブラリにアップロードされた画像が含まれます。

最初のアクティビティ作成時に表示される URL は、配信に使用される URL とは異なります。 この URL は、アクティビティの同期時に本番稼働用 Scene7 URL に更新されます。

例えば、最初の URL は次の例のように表示されます。

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

アクティビティの同期後、配信 URL は次の例のように表示されます。

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

レコメンデーションでは、DIV、SECTION、ARTICLE の各タグで「次で置換」をサポートしています。

**注意：**&#x200B;画像を置き換えるには、Adobe Scene7 Publishing System アカウントが必要です。

### [!UICONTROL HTML Offer]

[!UICONTROL Content Library]から別のオファーを選択します。

**注意：** HTML オファーは [!DNL Target] サーバーに格納されます。

HTML オファーは最大256 KBまで可能です。

### レコメンデーション

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内にレコメンデーションを含めます。 詳しくは、[オファーとしてのレコメンデーション](/help/main/c-recommendations/recommendations-as-an-offer.md)をご覧ください。

### [!UICONTROL Experience Fragment]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。 詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL Layout]

以下のオプションがあります。

### [!UICONTROL Rearrange]

要素を、同じ親要素または DIV 内の別の場所にドラッグします。 再配置される要素用の場所を空けるために、他の要素の位置が調整されます。

**メモ**：再配置されたアイテムでは、クリック トラッキングは機能しません。

現在、[!UICONTROL Rearrange]や[!UICONTROL Move]などの特定のVEC アクションでは、ソース要素と宛先の親要素の兄弟エレメントが完全に読み込まれていると仮定しています。 親DOM要素（ソースまたは宛先）の下で遅延読み込みが発生した場合、これらのVEC アクションは一貫性のない動作を引き起こす可能性があります。 私たちは、遅延読み込みDOM要素でVEC アクションを動作させるためのより信頼性の高いアプローチに取り組んでいます。 一時的な回避策として、これらのシナリオで[!UICONTROL Custom Code]を使用してエクスペリエンスをレンダリングできます。

### [!UICONTROL Resize]

ページの要素のサイズを変更します。 [!UICONTROL Resize]を選択すると、要素の右下隅にハンドルが表示され、そのコーナーをドラッグしてサイズを変更できます。 Shift キーを押しながら操作すると、縦横比が維持されます。

**注意：**&#x200B;インライン要素はサイズ変更できません。

### [!UICONTROL Move] {#move}

ページ上の要素を移動します。 [!UICONTROL Rearrange] オプションとは異なり、[!UICONTROL Move]は、移動される要素のスペースを確保するために他の要素を移動しません。 移動を細かく調整するには、矢印キーを使用します。 （計画的な機能強化：移動した要素が他の要素の背後に隠れないようにするためのサポート。）

CSS制限で要素を親エレメント内に残す必要がある場合など、特定の状況では、要素を親エレメント外に移動することはできません。 CSS プロパティ `overflow: hidden` を持つコンテナの外側に要素を移動することはできません。

DOM要素の遅延読み込みによる[!UICONTROL Move]および[!UICONTROL Rearrange] アクションとの一貫性のない動作について詳しくは、上記の[!UICONTROL Rearrange]を参照してください。

### [!UICONTROL Hide]

要素を非表示にします。 空白は残りますが、コンテンツは削除されます。

### [!UICONTROL Remove]

要素を削除します。 画像の背後の空白が削除され、要素のあった領域が折りたたまれます。

**注意：**「従来」の mbox（Target Classic キャンペーンで作成した mbox）内の項目は、このオプションを使用して削除することができません。

## [!UICONTROL Expand Section]

現在選択している要素に加えて、親要素を選択します。 親要素を選択しているときは、その要素のすべての子が自動的に選択されます。 選択の拡張は繰り返し実行できます。

## [!UICONTROL Navigate to Link]

リンク先を開きます。

## [!UICONTROL Undo]／[!UICONTROL Redo]

編集セッション中にアクティビティにおこなった変更を取り消します。 以前に取り消した変更をやり直すこともできます。

## 注意点 {#considerations}

* オファーに HTML コンテンツが含まれる場合、詳しくは、[at.js の仕組み](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} の「at.js による HTML コンテンツを使用したオファーのレンダリング方法」を参照してください。

## カスタム要素のサポート {#custom}

VECでは、[Web コンポーネント ](https://developer.mozilla.org/ja/docs/Web/Web_Components)をサポートしており、カスタム要素とカスタム要素の内部の要素でパーソナライズされたエクスペリエンスとオファーを作成およびテストできます。 この機能は、すべての[!DNL Target] アクティビティタイプに対してVECで使用できます。

>[!NOTE]
>
>カスタム要素に対するVEC サポートは、[at.js バージョン ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank} 2.7.0 （またはそれ以降） {target=_blank}でサポートされています。 web サイトに必要なバージョンがデプロイされていることを確認します。 [Visual Experience Composer ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)を使用している場合は、必要なバージョンのat.jsもデプロイされている必要があります。 上記のVEC オプションは表示されず、サポートされていないバージョンのat.jsで使用できます。
>
>カスタム要素に対するVEC サポートは、現在[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank}ではサポートされていません。

ほとんどのVEC アクションは、カスタムイベントおよびカスタムイベント内でサポートされていますが、次の例外があります。

次のアクションは、カスタム要素では使用できません。

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

次のアクションは、カスタム要素の中では使用できません。

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## DOM パスを使用したエレメントの移動 {#dom-path}

ページで要素をクリックすると、VEC オプションメニューが表示されます。 さらに、要素をクリックすると、対応する DOM パスがページの下部に表示されます。

![DOM パス](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

VEC で DOM パスの上にマウスポインターを置くと、対応する要素が青色のボックスで強調表示されます。 その要素をクリックすると、要素がオレンジ色のボックスで強調表示され、前述のように VEC オプションメニューが表示されます。

DOM パスを使用すれば、VEC 内で任意の親要素、兄弟要素、子要素に容易に移動できます。

DOM パス機能は、[クリックの追跡](/help/main/c-activities/r-success-metrics/click-tracking.md)を設定するときにも使用できます。
