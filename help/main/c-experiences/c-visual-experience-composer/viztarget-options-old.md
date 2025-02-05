---
keywords: visual experience composer オプション；experience composer オプション；experience options；テキストの編集；html の編集；テキストまたは html の編集；背景色の編集；要素の挿入；リンクの編集；visual experience composer リンク；css クラスの編集；オファーの交換；画像の交換；画像の交換；項目の削除；項目の非表示；項目の非表示；項目の並べ替え；要素の移動；要素のサイズ変更；要素の拡大；選択；移動；移動；リンク；元ににする；やり直す；やりす/やりす；カスタムイベント；web コンポーネント；オファー決定；offer decisioning
description: ' [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）で利用できるオプションを確認します。'
title: '[!UICONTROL Visual Experience Composer] （VEC）オプションの使用方法？'
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2667'
ht-degree: 55%

---

# Visual Experience Composer のオプション

[!DNL Adobe Target] [!UICONTROL Visual Experience Composer] （VEC）でページ要素をクリックすると、その要素タイプで使用できるオプションがメニューに表示されます。 さらに、ページの下部に DOM パスが表示されるので、ページ構造を簡単にナビゲートできます。

様々な [!UICONTROL Visual Experience Composer] （VEC）アクションが適切なメニューオプションにグループ化され、ジョブの迅速化と効率化を実現します。

![VEC オプションメニュー](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>使用できるオプションは、作成または編集しているアクティビティタイプによって異なります。

## [!UICONTROL Edit]

以下のオプションがあります。

### [!UICONTROL Text/HTML] {#edit-text-html}

要素の HTML コード（テキスト領域、ボタン、リンクのテキストなど）を変更します。

HTML コードだけでなく、カスタム JavaScript を編集および挿入することもできます。

[!UICONTROL A/B] アクティビティと [!UICONTROL Experience Targeting] アクティビティでテキストとHTMLを編集する場合は、いくつかのリッチテキスト書式設定オプションを使用できます。 フォントの選択、フォントスタイルの選択、テキストの整列方法の変更およびその他の標準的なテキスト書式オプションの設定が可能です。HTML を変更する際に、HTML のコードビューとリッチ編集ビューを切り替えることができます。

次の HTML5 タグをネストできます。

| タグ | ネスト可能なタグ |
| --- | --- |
| `<a>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>`、`<div>`、`<figure>`、`<figcaption>` |
| `<ins>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>` |
| `<del>` | `<ul>`、`<ol>`、`<menu>`、`<h1-h6>`、`<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

カラーピッカーを使用して、背景色を選択または設定します。カラースウォッチを選択して、RGB 値またはカラー 16 進コードを使用して調整できます。カラーピッカーの赤 x は、背景を透明にします。

**注意：**&#x200B;背景画像が設定されている要素に対しては、このオプションは利用できません。

### [!UICONTROL Styles] {#styles}

[!UICONTROL Styles] パネルを使用して、選択した要素の既存のスタイルの値を表示または編集します。 その他のスタイルを追加することもできます。

[!UICONTROL Styles] パネルにアクセスするには、VEC 内からページ要素をクリックして、**[!UICONTROL Edit]**/**[!UICONTROL Styles]** をクリックします。

[!UICONTROL Styles] パネルが VEC の右側に表示されます。 このパネルには、編集または選択した要素に追加できるスタイルのリストが含まれています。リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

![スタイルパネル](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

異なるスタイルを適用する場合は、任意のセクションを変更した後に、[!UICONTROL Styles] パネルの右上隅に表示される [!UICONTROL Revert] アイコンをクリックすることで、いつでも変更を元に戻すことができます。 [!UICONTROL Revert] アイコンをクリックすると、現在のセクションのパネルに対するすべての変更が元に戻ります。

後述のように、各セクションを展開して、スタイルを編集または追加します。変更を保存するには、パネルの上部にある「[!UICONTROL Back]」アイコンをクリックしてパネルのメインディスプレイに戻り、「**[!UICONTROL Save]**」をクリックします。

メインパネルと、様々なセクションパネルの各オプションの横にある青い点は、対応するスタイルが変更されたことを示します。 この視覚的なインジケーターにより、[!UICONTROL Save] をクリックする前に変更を簡単に確認できます。

>[!NOTE]
>
>レイアウト変更、背景色、サイズ変更、移動のクイックアクションは、VEC メニューの個別のアクションとしても使用できます。これらのオプションは、個別のアクションとして使用することも、ここで説明するようにスタイルメニューを使用することもできます。

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

  要素のタイポグラフィを変更します。タイポグラフィの編集は手軽におこなえます。

  リッチテキストエディター（テキストを編集/HTMLを編集）は微調整に使用できますが、このオプションを使用すると、要素全体を変更するクイックアクションを使用できます。 （テキスト全体ではなく）テキストの一部にのみタイポグラフィの変更を適用する場合は、[リッチテキストエディター](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)を使用します。

  次のタイポグラフィスタイルを編集できます。

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] （カラーコードを指定するか、カラーピッカーを使用します）
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  選択した要素の余白を変更します。左、右、下、上の余白を変更できます。

  各余白のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （スライダーをドラッグして余白を設定するか、各余白のピクセル数を指定します）

  余白は正と負の値をサポートします。

  Target は、rem、pc、em などのその他のサイズ単位もサポートしています。 これらの単位について詳しくは、[Web スタイルシートの CSS のヒントとテクニック ](https://www.w3.org/Style/Examples/007/units.en.html) を参照してください。

* **[!UICONTROL Padding]**

  選択した要素のパディングを変更します。左、右、下、上のパディングを変更できます。

  スライダーをドラッグしてパディングを設定するか、パディングのピクセル数を指定します。

  パディングは 0 以上の幅に対応します。

  Target は、rem、pc、em などの [ その他のサイズ単位 ](https://www.w3.org/Style/Examples/007/units.en.html) もサポートしています。

* **[!UICONTROL Border]**

  パネルの上部にある境界線アイコンをクリックして、選択した要素の境界線を変更します。

  境界線ごとに（上、右、下、左）、次のスタイルを編集できます。

   * [!UICONTROL Border style] （なし、非表示、点線、破線、実線、二重線）
   * [!UICONTROL Border color] （カラーコードを指定するか、カラーピッカーを使用します）
   * [!UICONTROL Border width] （スライダーをドラッグして境界線の幅を選択するか、幅をピクセル単位で指定します）

  境界線は 0 以上の幅に対応します。

  Target は、rem、pc、em などの [ その他のサイズ単位 ](https://www.w3.org/Style/Examples/007/units.en.html) もサポートしています。

* **[!UICONTROL Position]**

  選択した要素を現在の位置から移動します。要素の上、下、左、右、および [Z インデックス ](https://www.w3schools.com/cssref/pr_pos_z-index.asp) の位置を変更できます。

  「[!UICONTROL Static]」ドロップダウンリストをクリックして、次の位置オプションから選択します。

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  各位置のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （スライダーをドラッグして要素を配置するか、要素を移動するピクセル数を指定します）

  位置は正と負の値をサポートします。

  Target は、rem、pc、em などの [ その他のサイズ単位 ](https://www.w3.org/Style/Examples/007/units.en.html) もサポートしています。

* **[!UICONTROL Size]**

  選択した要素の幅と高さを変更します。

  [!UICONTROL Width] と [!UICONTROL Height] の横にあるドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL Auto]
   * [!UICONTROL Value] （スライダーをドラッグして要素のサイズを変更するか、各ディメンションのピクセル数を指定します）

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

  CSS エディターには、スタイルパネルでおこなった変更が表示されます。下の図では、フォントサイズ、上の境界線、画像サイズが変更されました。

  ![変更を反映した CSS エディター](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  前の図の「[!UICONTROL Typography]」、「[!UICONTROL Border]」、「[!UICONTROL Size]」の各オプションの横にある青い点に注意してください。 これらのドットは、これらのセクションが変更されたことを示します。 これらのセクションパネルを開くと、変更した特定のオプションの横に青いドットが表示されます。

  目的のスタイルが [!UICONTROL Styles] ージのデフォルトで使用できない場合は、独自のコードを入力できます。

  CSS エディターには、現在のセッションの詳細のみが表示されます。 変更を保存してエディターを再度開いた場合、同じ要素を再度選択しても、前の変更に関する詳細はエディターには表示されません。

  >[!IMPORTANT]
  >
  >CSS エディターを使用して背景画像を適用できますが、ちらつきが生じる場合があります。デプロイする前に変更をテストしてください。

### [!UICONTROL CSS Class]

要素で使用する事前定義 CSS クラスを指定します。複数の要素が選択されている場合は、複数の CSS クラスをスペースで区切ります。

[!UICONTROL A/B]、[!UICONTROL Automated Personalization]、[!UICONTROL Multivariate Test] の各アクティビティで使用できます。

### [!UICONTROL Link]

リンクの URL を変更します。

「リンクを編集」を使用して、同じ画像要素を指定するセレクターを更新します。ただし、異なる画像要素へのリンクはサポートされていません。別の画像要素にリンクするには、コードエディターから元のアクションを削除し、[!UICONTROL Visual Experience Composer] を使用して他の画像要素にアクションを適用します。

## [!UICONTROL Insert Before]

以下のオプションがあります。

### [!UICONTROL Offer Decision]

offer decisioningを使用して顧客に最高のオファーとエクスペリエンスを提供する [ で作成したオファー  [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} を追加します。

**メモ：** このオプションは、[ 手動 [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティを編集または作成する場合にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、「[ オファー決定の使用 ](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) を参照してください。

### [!UICONTROL Image]、[!UICONTROL HTML] および [!UICONTROL Text]

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページ上の要素を選択し、「[!UICONTROL Insert Before]」をクリックして、画像、HTMLまたはテキストを挿入するかどうかを選択します。 挿入された要素は、選択した要素の前に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。ページが正しく表示されるためには、有効な HTML を指定する必要があります。アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations] は、DIV、SECTION および ARTICLE タグのコンテンツの [!UICONTROL Insert Before] をサポートしています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

### レコメンデーション

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

### [!UICONTROL Experience Fragment]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL Insert After]

以下のオプションがあります。

### [!UICONTROL Offer Decision]

offer decisioningを使用して顧客に最高のオファーとエクスペリエンスを提供する [ で作成したオファー  [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} を追加します。

**メモ：** このオプションは、[ 手動 [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティを編集または作成する場合にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、「[ オファー決定の使用 ](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) を参照してください。

### [!UICONTROL Image]、[!UICONTROL HTML] および [!UICONTROL Text]

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページ上の要素を選択し、「[!UICONTROL Insert After]」をクリックして、画像、HTMLまたはテキストを挿入するかどうかを選択します。 挿入された要素は、選択した要素の後に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。ページが正しく表示されるためには、有効な HTML を指定する必要があります。アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations] は、DIV、SECTION および ARTICLE タグのコンテンツの [!UICONTROL Insert After] をサポートしています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

### レコメンデーション

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

### [!UICONTROL Experience Fragment]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL Replace Content]

以下のオプションがあります。

### [!UICONTROL Offer Decision]

offer decisioningを使用して顧客に最高のオファーとエクスペリエンスを提供する [ で作成したオファー  [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} を追加します。

**メモ：** このオプションは、[ 手動 [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) （XT）アクティビティを編集または作成する場合にのみ使用できます。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、「[ オファー決定の使用 ](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) を参照してください。

### [!UICONTROL Image]

コンテンツライブラリから別の画像を選択します。スワップに利用できる画像には、Experience Cloud アセットフォルダーまたは Target のコンテンツライブラリにアップロードされた画像が含まれます。

最初のアクティビティ作成時に表示される URL は、配信に使用される URL とは異なります。この URL は、アクティビティの同期時に実稼動用 Scene7 URL に更新されます。

例えば、最初の URL は次の例のように表示されます。

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

アクティビティの同期後、配信 URL は次の例のように表示されます。

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations では、DIV、SECTION、ARTICLE の各タグで「次で置換」をサポートしています。

**注意：**&#x200B;画像を置き換えるには、Adobe Scene7 Publishing System アカウントが必要です。

### [!UICONTROL HTML Offer]

[!UICONTROL Content Library] ージから別のオファーを選択します。

**注意：** HTML オファーは [!DNL Target] サーバーに格納されます。

HTMLオファーのサイズは最大 256 KB です。

### レコメンデーション

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

### [!UICONTROL Experience Fragment]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL Layout]

以下のオプションがあります。

### [!UICONTROL Rearrange]

要素を、同じ親要素または DIV 内の別の場所にドラッグします。再配置される要素用の場所を空けるために、他の要素の位置が調整されます。

**メモ**：並べ替えられた項目では、クリックの追跡は機能しません。

現在、[!UICONTROL Rearrange] や [!UICONTROL Move] などの特定の VEC アクションでは、ソースと宛先の親要素の兄弟要素が完全に読み込まれることを前提としています。 遅延読み込みが親 DOM 要素（ソースまたは宛先）の下で発生した場合、これらの VEC アクションによって動作に一貫性がなくなる可能性があります。 私たちは、遅延読み込みされた DOM 要素で VEC アクションを機能させるための、より信頼性の高いアプローチに取り組んでいます。 一時的な回避策として、これらのシナリオで [!UICONTROL Custom Code] を使用して、エクスペリエンスをレンダリングできます。

### [!UICONTROL Resize]

ページの要素のサイズを変更します。「[!UICONTROL Resize]」を選択すると、要素の右下隅にハンドルが表示され、隅をドラッグしてサイズを変更できます。 Shift キーを押しながら操作すると、縦横比が維持されます。

**注意：**&#x200B;インライン要素はサイズ変更できません。

### [!UICONTROL Move] {#move}

ページ上の要素を移動します。[!UICONTROL Rearrange] オプションとは異なり、[!UICONTROL Move] は移動する要素の場所を確保するために他の要素を移動しません。 移動を細かく調整するには、矢印キーを使用します。（計画的な機能強化：移動された要素が他の要素の背後に隠れないようにするサポート）

CSS 制限により要素をその親要素の内側に残す必要がある場合など、特定の状況では、要素を親要素の外側に移動することはできません。 CSS プロパティ `overflow: hidden` を持つコンテナの外側に要素を移動することはできません。

DOM 要素の遅延読み込みによる [!UICONTROL Move] アクションと [!UICONTROL Rearrange] アクションの動作が一貫していない場合の詳細は、上記の [!UICONTROL Rearrange] を参照してください。

### [!UICONTROL Hide]

要素を非表示にします。空白は残りますが、コンテンツは削除されます。

### [!UICONTROL Remove]

要素を削除します。画像の背後の空白が削除され、要素のあった領域が折りたたまれます。

**注意：**「従来」の mbox（Target Classic キャンペーンで作成した mbox）内の項目は、このオプションを使用して削除することができません。

## [!UICONTROL Expand Section]

現在選択している要素に加えて、親要素を選択します。親要素を選択しているときは、その要素のすべての子が自動的に選択されます。選択の拡張は繰り返し実行できます。

## [!UICONTROL Navigate to Link]

リンク先を開きます。

## [!UICONTROL Undo]／[!UICONTROL Redo]

編集セッション中にアクティビティにおこなった変更を取り消します。以前に取り消した変更をやり直すこともできます。

## 注意点 {#considerations}

* オファーにHTMLコンテンツが含まれている場合、詳しくは [at.js の仕組み ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} の「HTMLコンテンツを使用したオファーのレンダリング方法」を参照してください。

## カスタム要素のサポート {#custom}

VEC では、カスタム要素およびカスタム要素内の要素に対して、パーソナライズされたエクスペリエンスとオファーを作成およびテストできる [Web コンポーネント ](https://developer.mozilla.org/ja/docs/Web/Web_Components) をサポートしています。 この機能は、[!DNL Target] のすべてのアクティビティタイプに対して VEC で使用できます。

>[!NOTE]
>
>カスタム要素の VEC サポートは [at.js バージョン ](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=ja){target=_blank}2.7.0 （またはそれ以降）でサポートされ {target=_blank} います。 Web サイトに必要なバージョンがデプロイされていることを確認します。 [Visual Experience Composer ヘルパー拡張機能 ](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) を使用している場合は、必要なバージョンの at.js もデプロイしている必要があります。 上記の VEC オプションは表示されず、サポートされていないバージョンの at.js では使用できません。
>
>カスタム要素の VEC サポートは、現在、[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=ja){target=_blank} ではサポートされていません。

ほとんどの VEC アクションは、次の例外を除き、カスタムイベントでサポートされ、カスタムイベント内でサポートされています。

次のアクションは、カスタム要素では使用できません。

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

次のアクションは、カスタム要素内では使用できません。

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## DOM パスを使用して要素をナビゲートする {#dom-path}

ページで要素をクリックすると、VEC オプションメニューが表示されます。さらに、要素をクリックすると、対応する DOM パスがページの下部に表示されます。

![DOM パス](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

VEC で DOM パスの上にマウスポインターを置くと、対応する要素が青色のボックスで強調表示されます。その要素をクリックすると、要素がオレンジ色のボックスで強調表示され、前述のように VEC オプションメニューが表示されます。

DOM パスを使用すれば、VEC 内で任意の親要素、兄弟要素、子要素に容易に移動できます。

DOM パス機能は、[クリックの追跡](/help/main/c-activities/r-success-metrics/click-tracking.md)を設定するときにも使用できます。
