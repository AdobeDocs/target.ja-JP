---
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
description: Adobe Target Visual Experience Composer（VEC）でページ要素をクリックすると、その要素のタイプで利用可能なメニューオプションが表示されます。
title: Adobe Target Visual Experience Composer（VEC）オプション
feature: null
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '2404'
ht-degree: 95%

---


# Visual Experience Composer のオプション{#visual-experience-composer-options}

Visual Experience Composer（VEC）でページ要素をクリックすると、その要素のタイプで利用可能なメニューのオプションが表示されます。さらに、ページの下部に DOM パスが表示されるので、ページ構造を簡単にナビゲートできます。

## VEC オプション

Visual Experience Composer（VEC）の様々なアクションが適切なメニューオプションにグループ化されており、それらを通じてジョブを迅速かつ効率的に実行できます。

![VEC オプションメニュー](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>使用可能なオプションは、編集するアクティビティのタイプによって異なります。

### 編集

以下のオプションがあります。

#### テキスト／HTML {#edit-text-html}

要素の HTML コード（テキスト領域、ボタン、リンクのテキストなど）を変更します。

HTML コードだけでなく、カスタム JavaScript を編集および挿入することもできます。

[!UICONTROL A/B] および[!UICONTROL エクスペリエンスターゲット設定]アクティビティのテキストおよび HTML を編集する際に、いくつかのリッチテキスト書式オプションを利用できます。フォントの選択、フォントスタイルの選択、テキストの整列方法の変更およびその他の標準的なテキスト書式オプションの設定が可能です。HTML を変更する際に、HTML のコードビューとリッチ編集ビューを切り替えることができます。

次の HTML5 タグをネストできます。

| タグ | ネスト可能なタグ |
| --- | --- |
| `<a>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>`、`<div>`、`<figure>`、`<figcaption>` |
| `<ins>` | `<h1-h6>`、`<p>`、`<ul>`、`<ol>`、`<menu>` |
| `<del>` | `<ul>`、`<ol>`、`<menu>`、`<h1-h6>`、`<p>` |
| `<label>` | `<p>` |

#### 背景色

カラーピッカーを使用して、背景色を選択または設定します。カラースウォッチを選択して、RGB 値またはカラー 16 進コードを使用して調整できます。カラーピッカーの赤 x は、背景を透明にします。

**注意：**&#x200B;背景画像が設定されている要素に対しては、このオプションは利用できません。

#### スタイル {#styles}

[!UICONTROL スタイル]パネルを使用すると、選択した要素の既存のスタイルの値を表示または編集できます。その他のスタイルを追加することもできます。

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

[!UICONTROL スタイル]パネルは VEC の右側に表示されます。このパネルには、編集または選択した要素に追加できるスタイルのリストが含まれています。リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

![スタイルパネル](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

異なるスタイルを適用するときは、セクションを変更した後で、[!UICONTROL スタイル]パネルの右上隅に表示される「[!UICONTROL 元に戻す]」アイコンをクリックして、変更をいつでも元に戻すことができます。「[!UICONTROL 元に戻す]」アイコンをクリックすると、現在のセクションのパネルでおこなった変更がすべて元に戻されるので、注意してください。

後述のように、各セクションを展開して、スタイルを編集または追加します。変更を保存するには、パネル上部の戻るアイコンをクリックしてパネルのメイン表示に戻り、「**[!UICONTROL 保存]**」をクリックします。

様々なセクションパネルの各オプションの横やメインパネルに表示される青いドットは、対応するスタイルを変更したことを示しています。これにより、「[!UICONTROL 保存]」をクリックする前に変更内容を容易に確認できます。

>[!NOTE]
>
>レイアウト変更、背景色、サイズ変更、移動のクイックアクションは、VEC メニューの個別のアクションとしても使用できます。これらのオプションを個別のアクションとして利用することも、ここで説明するようにスタイルメニューを使用することもできます。

* **背景**

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

* **タイポグラフィ**

   要素のタイポグラフィを変更します。タイポグラフィの編集は手軽におこなえます。

   微調整にリッチテキストエディター（「テキスト／HTML を編集」）を使用できますが、要素全体を手軽に変更するには、このオプションを利用できます。（テキスト全体ではなく）テキストの一部にのみタイポグラフィの変更を適用する場合は、[リッチテキストエディター](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)を使用します。

   次のタイポグラフィスタイルを編集できます。

   * フォントサイズ
   * フォントの太さ
   * フォントスタイル
   * 色（カラーコードを指定するか、カラーピッカーを使用）
   * 単語の間隔
   * 行の高さ
   * テキストの整列

* **余白**

   選択した要素の余白を変更します。左、右、下、上の余白を変更できます。

   各余白のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * 自動
   * 値（スライダーをドラッグして余白を設定するか、余白ごとにピクセル数を指定）

   余白は正と負の値をサポートします。

   Target では、rem、pc、em などの他のサイズ単位もサポートします。For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **パディング**

   選択した要素のパディングを変更します。左、右、下、上のパディングを変更できます。

   スライダーをドラッグしてパディングを設定するか、パディングのピクセル数を指定します。

   パディングは 0 以上の幅に対応します。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **境界線**

   パネルの上部にある境界線アイコンをクリックして、選択した要素の境界線を変更します。

   境界線ごとに（上、右、下、左）、次のスタイルを編集できます。

   * 境界線のスタイル（なし、非表示、点線、破線、実線、二重線）
   * 境界線の色（カラーコードを指定するか、カラーピッカーを使用）
   * 境界線の幅（スライダーをドラッグして境界線の幅を選択するか、幅をピクセル単位で指定）

   境界線は 0 以上の幅に対応します。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **位置**

   選択した要素を現在の位置から移動します。You can change the element&#39;s top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

   「[!UICONTROL 静的]」ドロップダウンリストをクリックして、次の位置オプションから選択します。

   * 静的
   * 相対
   * 絶対
   * 固定
   * 固定

   各位置のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * 自動
   * 値（スライダーをドラッグして要素の位置を設定するか、要素を移動するピクセル数を指定）

   位置は正と負の値をサポートします。

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **サイズ**

   選択した要素の幅と高さを変更します。

   「[!UICONTROL 幅]」と「[!UICONTROL 高さ]」の横のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * 自動
   * 値（スライダーをドラッグして要素のサイズを設定するか、各寸法のピクセル数を指定）

* **フィルター**

   各フィルターオプションのスライダーをドラッグするか、目的の割合（％）を指定します。

   * セピア
   * コントラスト
   * 明るさ
   * グレースケール
   * ぼかし
   * 不透明度
   * 反転
   * 色相回転
   * 彩度

* **CSS エディター**

   リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

   CSS エディターには、スタイルパネルでおこなった変更が表示されます。下の図では、フォントサイズ、上の境界線、画像サイズが変更されました。

   ![変更を反映した CSS エディター](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   先ほどの図で、「[!UICONTROL タイポグラフィ]」、「[!UICONTROL 境界線]」、「[!UICONTROL サイズ]」の各オプションの横に青いドットがあります。このドットは、これらのセクションに変更を加えたことを示します。これらのセクションパネルを開くと、変更した特定のオプションの横に青いドットが表示されます。

   目的のスタイルが[!UICONTROL スタイル]パネルにデフォルトで用意されていない場合は、独自のコードを入力できます。

   CSS エディターには現在のセッションの詳細のみ表示される点に注意してください。変更を保存してエディターを再度開いた場合、同じ要素を再度選択しても、前の変更に関する詳細はエディターには表示されません。

   >[!I重要]
   >
   >CSS エディターを使用して背景画像を適用できますが、ちらつきが生じる場合があります。デプロイする前に変更をテストしてください。

#### CSS クラス

要素で使用する事前定義 CSS クラスを指定します。複数の要素が選択されている場合は、複数の CSS クラスをスペースで区切ります。

[!UICONTROL A/B]、[!UICONTROL 自動パーソナライゼーション]、[!UICONTROL 多変量分析]の各テストアクティビティで使用できます。

#### リンク

リンクの URL を変更します。

「リンクを編集」を使用して、同じ画像要素を指定するセレクターを更新します。ただし、異なる画像要素へのリンクはサポートされていません。異なる画像要素にリンクするには、コードエディターから元のアクションを削除し、[!UICONTROL Visual Experience Composer] を使用して別の画像要素に対するアクションを適用します。

### 前に挿入

以下のオプションがあります。

#### 画像、HTML、テキスト

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページの要素を選択し、「[!UICONTROL 前に挿入]」をクリックして、画像、HTML、テキストのどれを挿入するかを選択します。挿入された要素は、選択した要素の前に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。ページが正しく表示されるためには、有効な HTML を指定する必要があります。アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations] では、DIV タグ、SECTION タグ、ARTICLE タグのコンテンツの[!UICONTROL 前に挿入]がサポートされています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

#### 推奨

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

#### エクスペリエンスフラグメント

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

### 後ろに挿入

以下のオプションがあります。

#### 画像、HTML、テキスト

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページの要素を選択し、「[!UICONTROL 後ろに挿入]」をクリックして、画像、HTML、テキストのどれを挿入するかを選択します。挿入された要素は、選択した要素の後に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。ページが正しく表示されるためには、有効な HTML を指定する必要があります。アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations] では、DIV タグ、SECTION タグ、ARTICLE タグのコンテンツの[!UICONTROL 後ろに挿入]がサポートされています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

#### 推奨

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

#### エクスペリエンスフラグメント

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

### 次で置換

以下のオプションがあります。

#### 画像

コンテンツライブラリから別の画像を選択します。スワップに利用できる画像には、Experience Cloud アセットフォルダーまたは Target のコンテンツライブラリにアップロードされた画像が含まれます。

最初のアクティビティ作成時に表示される URL は、配信に使用される URL とは異なります。この URL は、アクティビティの同期時に実稼動用 Scene7 URL に更新されます。

例えば、最初の URL は次の例のように表示されます。

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

アクティビティの同期後、配信 URL は次の例のように表示されます。

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations では、DIV、SECTION、ARTICLE の各タグで「次で置換」をサポートしています。

**注意：**&#x200B;画像を置き換えるには、Adobe Scene7 Publishing System アカウントが必要です。

#### HTML オファー

[!UICONTROL コンテンツライブラリ]から別のオファーを選択します。

**注意：** HTML オファーは [!DNL Target] サーバーに格納されます。

HTML オファーのサイズは最大 256 KB です。

#### 推奨

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

#### エクスペリエンスフラグメント

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

### レイアウト

以下のオプションがあります。

#### 整列

要素を、同じ親要素または DIV 内の別の場所にドラッグします。再配置される要素用の場所を空けるために、他の要素の位置が調整されます。

**注意：**&#x200B;クリックの追跡は、再配置されたアイテム上では機能しません。

#### サイズ変更

ページの要素のサイズを変更します。「[!UICONTROL サイズ変更]」を選択すると、要素の右下隅にハンドルが表示され、その隅をドラッグしてサイズを変更できます。Shift キーを押しながら操作すると、縦横比が維持されます。

**注意：**&#x200B;インライン要素はサイズ変更できません。

#### 移動 {#move}

ページ上の要素を移動します。「[!UICONTROL 整列]」オプションとは異なり、「[!UICONTROL 移動]」では、移動される要素用の場所を空けるために別の要素の位置が調整されることはありません。移動を細かく調整するには、矢印キーを使用します。（今後の拡張予定：移動後の要素が他の要素の背後に隠れないようにする予定です。）

状況によっては（CSS の制限により要素を親要素内に置いておく必要がある場合など）、要素を親要素の外側に移動できないこともあります。CSS プロパティ `overflow: hidden` を持つコンテナの外側に要素を移動することはできません。

#### 非表示

要素を非表示にします。空白は残りますが、コンテンツは削除されます。

#### 削除

要素を削除します。画像の背後の空白が削除され、要素のあった領域が折りたたまれます。

**注意：**「従来」の mbox（Target Classic キャンペーンで作成した mbox）内の項目は、このオプションを使用して削除することができません。

### セクションを展開

現在選択している要素に加えて、親要素を選択します。親要素を選択しているときは、その要素のすべての子が自動的に選択されます。選択の拡張は繰り返し実行できます。

### このリンクに移動

リンク先を開きます。

### 取り消し／やり直し

編集セッション中にアクティビティにおこなった変更を取り消します。以前に取り消した変更をやり直すこともできます。

## 注意点 {#considerations}

* オファーに HTML コンテンツが含まれる場合、詳しくは、[at.js の仕組み](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render) の「at.js による HTML コンテンツを使用したオファーのレンダリング方法」を参照してください。

## DOM パス {#dom-path} を使用して要素をナビゲートする

ページで要素をクリックすると、VEC オプションメニューが表示されます。さらに、要素をクリックすると、対応する DOM パスがページの下部に表示されます。

![DOM パス](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

VEC で DOM パスの上にマウスポインターを置くと、対応する要素が青色のボックスで強調表示されます。その要素をクリックすると、要素がオレンジ色のボックスで強調表示され、前述のように VEC オプションメニューが表示されます。

DOM パスを使用すれば、VEC 内で任意の親要素、兄弟要素、子要素に容易に移動できます。

DOM パス機能は、[クリックの追跡](/help/c-activities/r-success-metrics/click-tracking.md)を設定するときにも使用できます。