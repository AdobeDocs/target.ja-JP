---
keywords: Visual Experience Composer のオプション；Experience Composer のオプション；テキストの編集；HTML の編集；背景色の編集；要素の編集；リンクの編集；リンクの編集；CSS クラス；SWAP；画像の置き換え；画像の置き換え；項目の非表示；要素の移動；要素の変更；要素の変更；リンクナビゲート；移動；リンク；元に戻す；やり直し；元に戻す/やり直し；カスタムイベント；Web コンポーネント；オファーの決定；offer decisioning
description: で使用可能なオプションの詳細 [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) を参照してください。
title: 使用方法 [!UICONTROL Visual Experience Composer] (VEC) オプション
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '2932'
ht-degree: 61%

---

# Visual Experience Composer のオプション

ページ要素をクリックしたとき ( [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) の場合、その要素のタイプで使用できるメニューのオプションが表示されます。 さらに、ページの下部に DOM パスが表示されるので、ページ構造を簡単にナビゲートできます。

様々な [!UICONTROL Visual Experience Composer] (VEC) アクションが適切なメニューオプションにグループ化され、ジョブを迅速かつ効率的に実行できます。

![VEC オプションメニュー](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>使用できるオプションは、作成または編集するアクティビティのタイプによって異なります。

## [!UICONTROL 編集]

以下のオプションがあります。

### [!UICONTROL テキスト／HTML] {#edit-text-html}

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

### [!UICONTROL 背景色]

カラーピッカーを使用して、背景色を選択または設定します。カラースウォッチを選択して、RGB 値またはカラー 16 進コードを使用して調整できます。カラーピッカーの赤 x は、背景を透明にします。

**注意：**&#x200B;背景画像が設定されている要素に対しては、このオプションは利用できません。

### [!UICONTROL スタイル] {#styles}

[!UICONTROL スタイル]パネルを使用すると、選択した要素の既存のスタイルの値を表示または編集できます。その他のスタイルを追加することもできます。

次の手順で [!UICONTROL スタイル] パネルで、VEC 内からページ要素をクリックし、 **[!UICONTROL 編集]** > **[!UICONTROL スタイル]**.

[!UICONTROL スタイル]パネルは VEC の右側に表示されます。このパネルには、編集または選択した要素に追加できるスタイルのリストが含まれています。リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

![スタイルパネル](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

異なるスタイルを適用する場合、 [!UICONTROL 元に戻す] アイコン [!UICONTROL スタイル] パネルを使用して、任意のセクションを変更できます。 クリック [!UICONTROL 元に戻す] アイコンは、現在のセクションのパネルで行った変更をすべて元に戻します。

後述のように、各セクションを展開して、スタイルを編集または追加します。変更を保存するには、 [!UICONTROL 戻る] パネル上部のアイコンをクリックしてパネルのメイン表示に戻り、 **[!UICONTROL 保存]**.

様々なセクションパネルの各オプションの横にあるメインパネル上の青いドットは、対応するスタイルが変更されたことを示します。 この視覚的インジケーターを使用すると、クリックする前に変更を簡単に確認できます [!UICONTROL 保存].

>[!NOTE]
>
>レイアウト変更、背景色、サイズ変更、移動のクイックアクションは、VEC メニューの個別のアクションとしても使用できます。これらのオプションは、個別のアクションとして使用することも、ここで説明するスタイルメニューを使用することもできます。

* **[!UICONTROL 背景]**

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

* **[!UICONTROL タイポグラフィ]**

   要素のタイポグラフィを変更します。タイポグラフィの編集は手軽におこなえます。

   微調整にはリッチテキストエディター ( テキスト/HTMLを編集 ) を使用できますが、要素全体を変更するクイックアクションは、このオプションから使用できます。 （テキスト全体ではなく）テキストの一部にのみタイポグラフィの変更を適用する場合は、[リッチテキストエディター](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md)を使用します。

   次のタイポグラフィスタイルを編集できます。

   * [!UICONTROL フォントサイズ]
   * [!UICONTROL フォントの太さ]
   * [!UICONTROL フォントスタイル]
   * [!UICONTROL カラー] （カラーコードを指定するか、カラーピッカーを使用）
   * [!UICONTROL 単語の間隔]
   * [!UICONTROL 行の高さ]
   * [!UICONTROL テキストの整列]

* **[!UICONTROL 余白]**

   選択した要素の余白を変更します。左、右、下、上の余白を変更できます。

   各余白のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL 自動]
   * [!UICONTROL 値] （スライダーをドラッグして余白を設定するか、余白ごとにピクセル数を指定）

   余白は正と負の値をサポートします。

   Target は rem、pc、em などの他のサイズ単位もサポートします。 これらの単位の詳細については、 [Web スタイルシート CSS のヒントとテクニック](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL パディング]**

   選択した要素のパディングを変更します。左、右、下、上のパディングを変更できます。

   スライダーをドラッグしてパディングを設定するか、パディングのピクセル数を指定します。

   パディングは 0 以上の幅に対応します。

   Target もをサポートしています。 [その他のサイズ単位](https://www.w3.org/Style/Examples/007/units.en.html)rem、pc、em など。

* **[!UICONTROL 境界線]**

   パネルの上部にある境界線アイコンをクリックして、選択した要素の境界線を変更します。

   境界線ごとに（上、右、下、左）、次のスタイルを編集できます。

   * [!UICONTROL 境界線のスタイル] （なし、非表示、点線、破線、実線、二重線）
   * [!UICONTROL 境界線のカラー] （カラーコードを指定するか、カラーピッカーを使用）
   * [!UICONTROL 境界線の幅] （スライダーをドラッグして境界線の幅を選択するか、幅をピクセル単位で指定）

   境界線は 0 以上の幅に対応します。

   Target もをサポートしています。 [その他のサイズ単位](https://www.w3.org/Style/Examples/007/units.en.html)rem、pc、em など。

* **[!UICONTROL 位置]**

   選択した要素を現在の位置から移動します。要素の上、下、左、右および [Z — インデックス](https://www.w3schools.com/cssref/pr_pos_z-index.asp) 位置。

   「[!UICONTROL 静的]」ドロップダウンリストをクリックして、次の位置オプションから選択します。

   * [!UICONTROL 静的]
   * [!UICONTROL 相対]
   * [!UICONTROL 絶対]
   * [!UICONTROL 固定]
   * [!UICONTROL 固定]

   各位置のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL 自動]
   * [!UICONTROL 値] （スライダーをドラッグして要素を配置するか、要素を移動するピクセル数を指定します）

   位置は正と負の値をサポートします。

   Target もをサポートしています。 [その他のサイズ単位](https://www.w3.org/Style/Examples/007/units.en.html)rem、pc、em など。

* **[!UICONTROL サイズ]**

   選択した要素の幅と高さを変更します。

   「[!UICONTROL 幅]」と「[!UICONTROL 高さ]」の横のドロップダウンアイコンをクリックして、次のオプションから選択します。

   * [!UICONTROL 自動]
   * [!UICONTROL 値] （スライダーをドラッグして要素のサイズを設定するか、各寸法のピクセル数を指定します）

* **[!UICONTROL フィルター]**

   各フィルターオプションのスライダーをドラッグするか、目的の割合（％）を指定します。

   * [!UICONTROL セピア]
   * [!UICONTROL コントラスト]
   * [!UICONTROL 明るさ]
   * [!UICONTROL グレースケール]
   * [!UICONTROL ぼかし]
   * [!UICONTROL 不透明度]
   * [!UICONTROL 反転]
*
[!UICONTROL  色相回転]
   * [!UICONTROL 彩度]

* **[!UICONTROL CSS エディター]**

   リアルタイム CSS エディターを使用すると、カスケーディングスタイルシート（CSS）を使用している場合や開発者からコードを受け取った場合に、変更を表示したりスタイルを追加したりできます。

   CSS エディターには、スタイルパネルでおこなった変更が表示されます。下の図では、フォントサイズ、上の境界線、画像サイズが変更されました。

   ![変更を反映した CSS エディター](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   先ほどの図で、「[!UICONTROL タイポグラフィ]」、「[!UICONTROL 境界線]」、「[!UICONTROL サイズ]」の各オプションの横に青いドットがあります。これらのドットは、これらのセクションを変更したことを示します。 これらのセクションパネルを開くと、変更した特定のオプションの横に青いドットが表示されます。

   目的のスタイルが[!UICONTROL スタイル]パネルにデフォルトで用意されていない場合は、独自のコードを入力できます。

   CSS エディターには、現在のセッションの詳細のみが表示されます。 変更を保存してエディターを再度開いた場合、同じ要素を再度選択しても、前の変更に関する詳細はエディターには表示されません。

   >[!IMPORTANT]
   >
   >CSS エディターを使用して背景画像を適用できますが、ちらつきが生じる場合があります。デプロイする前に変更をテストしてください。

### [!UICONTROL CSS クラス]

要素で使用する事前定義 CSS クラスを指定します。複数の要素が選択されている場合は、複数の CSS クラスをスペースで区切ります。

[!UICONTROL A/B]、[!UICONTROL 自動パーソナライゼーション]、[!UICONTROL 多変量分析]の各テストアクティビティで使用できます。

### [!UICONTROL リンク]

リンクの URL を変更します。

「リンクを編集」を使用して、同じ画像要素を指定するセレクターを更新します。ただし、異なる画像要素へのリンクはサポートされていません。異なる画像要素にリンクするには、コードエディターから元のアクションを削除し、[!UICONTROL Visual Experience Composer] を使用して別の画像要素に対するアクションを適用します。

## [!UICONTROL 前に挿入]

以下のオプションがあります。

### [!UICONTROL オファーの決定]

を追加します。 [作成されたオファー [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} を使用して、offer decisioningを使用するお客様に最適なオファーとエクスペリエンスを提示します。

**注意：** このオプションは、編集または作成時に使用できます [手動 [!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL エクスペリエンスのターゲット設定]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) アクティビティのみ。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、 [オファーの決定を使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL 画像], [!UICONTROL HTML]、および [!UICONTROL テキスト]

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページの要素を選択し、「[!UICONTROL 前に挿入]」をクリックして、画像、HTML、テキストのどれを挿入するかを選択します。挿入された要素は、選択した要素の前に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。ページが正しく表示されるためには、有効な HTML を指定する必要があります。アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations] では、DIV タグ、SECTION タグ、ARTICLE タグのコンテンツの[!UICONTROL 前に挿入]がサポートされています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

### 推奨

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

### [!UICONTROL エクスペリエンスフラグメント]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL 後ろに挿入]

以下のオプションがあります。

### [!UICONTROL オファーの決定]

を追加します。 [作成されたオファー [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} を使用して、offer decisioningを使用するお客様に最適なオファーとエクスペリエンスを提示します。

**注意：** このオプションは、編集または作成時に使用できます [手動 [!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL エクスペリエンスのターゲット設定]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) アクティビティのみ。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、 [オファーの決定を使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL 画像], [!UICONTROL HTML]、および [!UICONTROL テキスト]

既存のコンテンツの変更に加えて、ページに任意の種類の要素を追加します。テキスト、コード、リストなどを追加して、テストにまったく異なるエクスペリエンスを作成できます。

ページの要素を選択し、「[!UICONTROL 後ろに挿入]」をクリックして、画像、HTML、テキストのどれを挿入するかを選択します。挿入された要素は、選択した要素の後に表示されます。

挿入された要素の動作はページの構造、CSS、その他のページ設定オプションに応じて異なります。ページが正しく表示されるためには、有効な HTML を指定する必要があります。アイテムを挿入した後は、必ずページをテストして、想定どおりに表示されることを確認してください。

[!UICONTROL Recommendations] では、DIV タグ、SECTION タグ、ARTICLE タグのコンテンツの[!UICONTROL 後ろに挿入]がサポートされています。

**注意：**&#x200B;画像を挿入するには、画像ライブラリにアクセスできるように [!DNL Adobe Scene7 Publishing System] が有効になっている必要があります。

### 推奨

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

### [!UICONTROL エクスペリエンスフラグメント]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL コンテンツを置換]

以下のオプションがあります。

### [!UICONTROL オファーの決定]

を追加します。 [作成されたオファー [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} を使用して、offer decisioningを使用するお客様に最適なオファーとエクスペリエンスを提示します。

**注意：** このオプションは、編集または作成時に使用できます [手動 [!UICONTROL A/B テスト]](/help/main/c-activities/t-test-ab/test-ab.md#types) または [[!UICONTROL エクスペリエンスのターゲット設定]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) アクティビティのみ。 このオプションは、他のアクティビティタイプでは使用できません。

詳しくは、 [オファーの決定を使用](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

コンテンツライブラリから別の画像を選択します。スワップに利用できる画像には、Experience Cloud アセットフォルダーまたは Target のコンテンツライブラリにアップロードされた画像が含まれます。

最初のアクティビティ作成時に表示される URL は、配信に使用される URL とは異なります。この URL は、アクティビティの同期時に実稼動用 Scene7 URL に更新されます。

例えば、最初の URL は次の例のように表示されます。

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

アクティビティの同期後、配信 URL は次の例のように表示されます。

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations では、DIV、SECTION、ARTICLE の各タグで「次で置換」をサポートしています。

**注意：**&#x200B;画像を置き換えるには、Adobe Scene7 Publishing System アカウントが必要です。

### [!UICONTROL HTML オファー]

[!UICONTROL コンテンツライブラリ]から別のオファーを選択します。

**注意：** HTML オファーは [!DNL Target] サーバーに格納されます。

HTMLオファーは最大 256 KB です。

### 推奨

A/B テスト（自動配分および自動ターゲットなど）およびエクスペリエンスのターゲット設定（XT）アクティビティ内に Recommendations を含めます。詳細については、「[オファーとしての Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md)」をご覧ください。

### [!UICONTROL エクスペリエンスフラグメント]

[!DNL Adobe Experience Manager]（AEM）[!DNL Target]で作成したエクスペリエンスフラグメントをアクティビティに挿入して、最適化やパーソナライゼーションを支援します。詳細については、「[AEM エクスペリエンスフラグメント](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md)」をご覧ください。

## [!UICONTROL レイアウト]

以下のオプションがあります。

### [!UICONTROL 整列]

要素を、同じ親要素または DIV 内の別の場所にドラッグします。再配置される要素用の場所を空けるために、他の要素の位置が調整されます。

**注意**:クリックの追跡は、再配置されたアイテム上では機能しません。

現在、特定の VEC アクション ( [!UICONTROL 並べ替え] および [!UICONTROL 移動]の場合、ソースと宛先の親要素の兄弟要素が完全に読み込まれているとします。 親 DOM 要素（ソースまたは宛先）の下で遅延読み込みが発生した場合、これらの VEC アクションによって動作に不整合が生じる可能性があります。 アドビでは、遅延読み込みされた DOM 要素で VEC アクションを機能させるための、より信頼性の高いアプローチに取り組んでいます。 一時的な回避策として、 [!UICONTROL カスタムコード] （エクスペリエンスをレンダリングする場合）。

### [!UICONTROL サイズ変更]

ページの要素のサイズを変更します。次を選択した場合： [!UICONTROL サイズ変更]の場合は、要素の右下隅にハンドルが表示され、その隅をドラッグしてサイズを変更できます。 Shift キーを押しながら操作すると、縦横比が維持されます。

**注意：**&#x200B;インライン要素はサイズ変更できません。

### [!UICONTROL 移動] {#move}

ページ上の要素を移動します。「[!UICONTROL 整列]」オプションとは異なり、「[!UICONTROL 移動]」では、移動される要素用の場所を空けるために別の要素の位置が調整されることはありません。移動を細かく調整するには、矢印キーを使用します。( 計画された機能強化：は、移動した要素が他の要素の背後に隠れないようにするためのサポートです )。

特定の状況（CSS の制限により要素を親要素内に置いておく必要がある場合など）では、要素を親要素の外側に移動することはできません。 CSS プロパティ `overflow: hidden` を持つコンテナの外側に要素を移動することはできません。

詳しくは、 [!UICONTROL 並べ替え] 以下との一貫性のない動作に関する詳細は、以下を参照してください。 [!UICONTROL 移動] および [!UICONTROL 並べ替え] DOM 要素の遅延読み込みによるアクション。

### [!UICONTROL 非表示]

要素を非表示にします。空白は残りますが、コンテンツは削除されます。

### [!UICONTROL 削除]

要素を削除します。画像の背後の空白が削除され、要素のあった領域が折りたたまれます。

**注意：**「従来」の mbox（Target Classic キャンペーンで作成した mbox）内の項目は、このオプションを使用して削除することができません。

## [!UICONTROL セクションを展開]

現在選択している要素に加えて、親要素を選択します。親要素を選択しているときは、その要素のすべての子が自動的に選択されます。選択の拡張は繰り返し実行できます。

## [!UICONTROL このリンクに移動]

リンク先を開きます。

## [!UICONTROL 取り消し]/[!UICONTROL やり直し]

編集セッション中にアクティビティにおこなった変更を取り消します。以前に取り消した変更をやり直すこともできます。

## 注意点 {#considerations}

* オファーにHTMLコンテンツが含まれる場合、「at.js によるHTMLコンテンツを使用したオファーのレンダリング方法」( [at.js の仕組み](https://developer.adobe.com/target/implement/client-side/atjs/how-atjs-works/how-atjs-works/){target=_blank} を参照してください。

## カスタム要素のサポート {#custom}

VEC はをサポートしています。 [Web コンポーネント](https://developer.mozilla.org/ja/docs/Web/Web_Components) を使用すると、カスタム要素およびカスタム要素内の要素に対して、パーソナライズされたエクスペリエンスとオファーを作成およびテストできます。 この機能は、VEC ですべての [!DNL Target] アクティビティのタイプ。

>[!NOTE]
>
>カスタム要素の VEC サポートは、 [at.js バージョン](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank} 2.7.0（以降）。 Web サイトに必要なバージョンがデプロイされていることを確認します。 を使用している場合、 [Visual Experience Composer ヘルパー拡張機能](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md)また、必要なバージョンの at.js をデプロイする必要があります。 上記の VEC オプションは表示されず、サポートされていないバージョンの at.js で使用できます。
>
>現在、カスタム要素の VEC サポートは、 [Adobe Experience Platform Web SDK](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/).

ほとんどの VEC アクションは、カスタムイベントとカスタムイベント内でサポートされますが、次の例外があります。

次のアクションは、カスタム要素では使用できません。

* [!UICONTROL 編集]
   * [!UICONTROL テキスト／HTML]
   * [!UICONTROL リンク]
   * [!UICONTROL ソースを編集]

* [!UICONTROL コンテンツを置換]

次のアクションは、カスタム要素内では使用できません。

* [!UICONTROL レイアウト]
   * [!UICONTROL 整列]

## DOM パス  を使用して要素をナビゲートする {#dom-path}

ページで要素をクリックすると、VEC オプションメニューが表示されます。さらに、要素をクリックすると、対応する DOM パスがページの下部に表示されます。

![DOM パス](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

DOM パスを使用すると、選択した要素に関する情報（タイプ、ID、クラス）をすばやく確認したり、DOM パスを上下に移動して目的の要素を選択したりできます。

VEC で DOM パスの上にマウスポインターを置くと、対応する要素が青色のボックスで強調表示されます。その要素をクリックすると、要素がオレンジ色のボックスで強調表示され、前述のように VEC オプションメニューが表示されます。

DOM パスを使用すれば、VEC 内で任意の親要素、兄弟要素、子要素に容易に移動できます。

DOM パス機能は、[クリックの追跡](/help/main/c-activities/r-success-metrics/click-tracking.md)を設定するときにも使用できます。
