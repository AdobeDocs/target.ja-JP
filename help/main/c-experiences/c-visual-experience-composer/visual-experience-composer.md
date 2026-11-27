---
keywords: visual experience composer;vec;wysiwyg
description: Adobe TargetでのVisual Experience Composer （VEC）の使用方法の基本について説明します。 VECは、パーソナライズされたエクスペリエンスを容易に構築できるWYSIWYGエディターです。
title: Visual Experience Composer （VEC）の使用方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: 'https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%
---
# [!UICONTROL Visual Experience Composer]を使い始める {#vec-overview}

>[!BEGINSHADEBOX]

**このページで：** [!UICONTROL Visual Experience Composer] （VEC）を開く方法、エクスペリエンスを編集する方法、ページの読み込みを管理する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）は、コードを編集することなく、web サイトやモバイル web ページでパーソナライズされたエクスペリエンスを直接作成およびテストするためのWYSIWYG エディターです。

[!DNL Target]件のアクティビティのエクスペリエンスとオファーは、要素のドラッグ&amp;ドロップ、コンテンツの入れ替え、ページレイアウトの変更によって作成されます。 このコンポーザーには、HTMLとJavaScriptを編集するためのオプションも用意されています。

## ブラウザーの要件 {#browser-requirements}

[!DNL Safari]は[!DNL Adobe Target] インターフェイスでサポートされています。 フォームベースのアクティビティは、[!DNL Safari]で作成できます。VECと[!UICONTROL Enhanced Experience Composer] （EEC）を除くすべての機能を使用できます。 VECが[!DNL Safari]で開かれている場合、オーバーレイを使用すると、エクスペリエンスを編集するために[!DNL Google Chrome]に切り替えるようユーザーに求められます。

[!DNL Firefox]などのブラウザーは、安全なサイト内の安全でないページなど、混在コンテンツを含むページがVECに表示されるのをブロックする場合があります。 ページが表示されない場合は、ブラウザーのアドレスバーのURLの横にあるアイコンをクリックし、**[!UICONTROL このページの保護を無効にする]**&#x200B;をクリックします。 この問題は、サイト訪問者に対するページの表示方法には影響しません。

## VECを開く {#open-the-vec}

VECでデフォルトで開くページを設定するには、「[!DNL Target] **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**」タブにデフォルトの[!UICONTROL Visual Experience Composer] URLを入力します。 デフォルトのURLが設定されていない場合、VECは空白のページで開き、URLを指定できます。

「ビジュアルエクスペリエンスコンポーザー」タブが強調表示され、デフォルト URL、拡張エクスペリエンスコンポーザー、混合コンテンツの読み込みの設定が表示された![管理ページ ](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## エクスペリエンスを編集 {#edit-experiences}

### エクスペリエンスの表示と命名 {#view-and-name-experiences}

**[!UICONTROL エクスペリエンス]** パネルのタブには、異なるオーディエンスや異なるエクスペリエンスでページがどのように表示されるかが表示されます。 各エクスペリエンスにわかりやすい名前を付けることで、リスト内での識別が容易になります。 例えば、ナビゲーションバーでホームリンクの位置をテストする場合、最初に表示されるエクスペリエンスには「最初にホームリンク」という名前を付けることができます。

![ エクスペリエンス B](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)の名前変更アイコンから開いた、最初にホームリンクという名前のエクスペリエンスダイアログの名前を変更

### 要素の選択と変更 {#select-and-modify-elements}

ページ上にカーソルを移動すると、コンテクストに応じたボックスが表示され、個々の要素がハイライトされます。 ハイライト表示されたエレメントをクリックすると、そのエレメントの種類の編集オプションが表示されます。 例えば、画像を選択し、**[!UICONTROL 画像オファーの変更]**&#x200B;をクリックすると、その画像に置き換わります。ボタンを選択すると、テキストの色を変更できます。

![選択した画像の上に表示される編集オプション ](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

ページに埋め込まれたiframe内のコンテンツは編集できません。 そのコンテンツを編集するには、iframe ドキュメントが[!DNL Target]対応であることを確認してから、iframe URLをVECに直接読み込みます。

VEC以外のページ構造の変更は、アクティビティで使用される場所に影響を与える可能性があります。 これらの場所が変更されると、[!DNL Target]は変更された要素を見つけられない可能性があり、エクスペリエンスの編集時に問題が発生する可能性があります。

### 参照とデザイン {#browse-and-design}

「**[!UICONTROL 参照]**」をクリックして、現在のページからアクセス可能なページ（配送ページやショッピングカートなど）に移動し、そこで変更をテストします。

![URL フィールドと前後の矢印を含むVECの参照モード ](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

参照モードでは、フライアウトメニューやミニカートなど、カーソルを合わせて表示される要素にもアクセスできます。 編集するページまたは要素に到達したら、**[!UICONTROL デザイン]**&#x200B;をクリックしてエクスペリエンスを編集します。

ホバー状態がJavaScriptに依存している場合は、**[!UICONTROL JavaScriptを無効にする]**&#x200B;が選択されていないことを確認してください。 JavaScriptに依存する要素を編集するには、Adobe Targetを有効にする必要があります。

使用可能な編集オプションについて詳しくは、[Visual Experience Composer オプション ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

## ページ読み込みを管理 {#manage-page-loading}

ページの読み込み中や読み込みに失敗した後も、一部の編集オプションを利用できます。 ページの読み込みをキャンセルして、待たずにこれらのオプションにアクセスすることもできます。

### ページの読み込み中またはページの読み込みに失敗した後にページを編集する {#loading}

ページの読み込みがVECで完了する前に、または読み込みに失敗した後に変更を加えることができます。例えば、カスタムコードが機能しなくなったためです。

使用可能な編集オプションを使用すると、次のことが可能になります。

* カスタムコードの追加やエクスペリエンスの名前の変更など、簡単な変更を行います
* アクセスできなくなったページから既存のカスタムコードをコピーする
* VECで読み込めないページを簡単に編集する

ページの読み込み中または読み込みに失敗した後も、**[!UICONTROL エクスペリエンス]** パネル、**[!UICONTROL コンポーネント]** パネル、**[!UICONTROL 設定]** オプションにアクセスできます。

### VEC内のページの読み込みをキャンセル {#cancel-loading}

VECでのページ読み込みをキャンセルすると、ページの読み込みが完了するのを待たずにアクティビティを編集できます。 これは次の場合に便利です。

* 既存の修正を微調整する
* 1つ以上の既存の修正を削除
* カスタムコードの挿入または編集
* 誤って入力されたページ URLの修正
* VECにページを読み込む前に、JavaScriptを有効または無効にします
* **[!UICONTROL ページ配信]**&#x200B;条件にテンプレートテストルールを追加
* EEC経由またはiframe専用モードでページを読み込む際に、グローバルな[!UICONTROL Enhanced Experience Composer] （EEC）トグルを上書きする

ページの読み込みがキャンセルされた後、ページの読み込みを待たずに、アクティビティ内のエクスペリエンスを切り替えることができます。 **[!UICONTROL 再読み込み]**&#x200B;をクリックして、ページをVECに再度表示します。

>[!IMPORTANT]
>
>ページの読み込みがキャンセルされた後にカスタムコードが編集されたり、その他の変更が行われた場合は、品質保証（QA）テストを実行して、変更が期待どおりに配信されていることを確認します。

ページの読み込みを停止するには、ページの読み込み中に&#x200B;**[!UICONTROL 読み込みをキャンセル]**&#x200B;をクリックします。 ページが再読み込みされない限り、現在の編集セッション中も、このアクティビティのページはアンロードされたままになります。

「**[!UICONTROL 再読み込み]**」をクリックして、現在のアクティビティでのエクスペリエンスの管理を再開するか、新しい変更を追加します。
