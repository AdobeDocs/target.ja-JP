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
source-git-commit: 140a7287246905d47bf02a84348627017a619386
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%
---
# [!UICONTROL Visual Experience Composer] （VEC）

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）は、コードを編集せずにweb サイトやモバイル web ページでパーソナライズされたエクスペリエンスを直接作成およびテストするためのWYSIWYG エディターです。

要素のドラッグ&amp;ドロップ、コンテンツの入れ替え、ページレイアウトの変更などにより、[!DNL Target] アクティビティのエクスペリエンスとオファーを作成します。 このコンポーザーには、HTMLとJavaScriptを編集するためのオプションも用意されています。

## ブラウザーの要件 {#browser-requirements}

[!DNL Safari]は[!DNL Adobe Target] インターフェイスでサポートされています。 [!DNL Safari]でフォームベースのアクティビティを作成し、VECと[!UICONTROL Enhanced Experience Composer] （EEC）を除くすべての機能を使用できます。 [!DNL Safari]でVisual Experience Composerを開くと、オーバーレイで[!DNL Google Chrome]に切り替えてエクスペリエンスを編集するように求められます。

[!DNL Firefox]などのブラウザーは、安全なサイト内の安全でないページなど、混在コンテンツを含むページがVECに表示されるのをブロックする場合があります。 ページが表示されない場合は、ブラウザーのアドレスバーのURLの横にあるアイコンをクリックし、**[!UICONTROL このページの保護を無効にする]**&#x200B;をクリックします。 この問題は、サイト訪問者に対するページの表示方法には影響しません。

## VECを開く {#open-the-vec}

VECでデフォルトで開くページを設定するには、「[!DNL Target] **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]**」タブにデフォルトの[!UICONTROL Visual Experience Composer] URLを入力します。

デフォルトのURLを設定しない場合、VECが開き、URLを指定できる空白のページが表示されます。

![ハイライトされた VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## エクスペリエンスを編集 {#edit-experiences}

### エクスペリエンスの表示と命名 {#view-and-name-experiences}

[!UICONTROL &#x200B; エクスペリエンス &#x200B;] パネルのタブを使用して、様々なオーディエンスや異なるエクスペリエンスでページがどのように表示されるかを確認します。 各エクスペリエンスにわかりやすい名前を付けて、リスト内で容易に識別できるようにします。

例えば、ナビゲーションバーでホームリンクの位置をテストする場合は、最初に表示されるエクスペリエンスに「最初にホームリンク」という名前を付けます。

![&#x200B; エクスペリエンスパネルでエクスペリエンスの名前を変更](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### 要素の選択と変更 {#select-and-modify-elements}

ページ上にカーソルを移動して、コンテクストを考慮するボックスで個々の要素をハイライト表示します。

ハイライト表示された要素をクリックすると、その要素タイプの編集オプションが表示されます。 例えば、画像を選択し、**[!UICONTROL 画像ソースを変更]**&#x200B;をクリックして置換するか、ボタンを選択してテキストの色を変更します。

![選択した要素のオプションの編集](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

ページに埋め込まれたiframe内のコンテンツは編集できません。 そのコンテンツを編集するには、iframe ドキュメントが[!DNL Target]対応であることを確認してから、iframe URLをVECに直接読み込みます。

VEC以外のページ構造の変更は、アクティビティで使用される場所に影響を与える可能性があります。 これらの場所が変更された場合、[!DNL Target]は変更した要素を見つけられない可能性があり、エクスペリエンスの編集時に問題が発生する可能性があります。

### 参照とデザイン {#browse-and-design}

「**[!UICONTROL 参照]**」をクリックして、現在のページからアクセス可能なページ（配送ページやショッピングカートなど）に移動し、そこで変更をテストします。

![VEC](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)での参照モード

参照モードでは、フライアウトメニューやミニカートなど、カーソルを合わせて表示される要素にもアクセスできます。 編集するページまたは要素に到達したら、**[!UICONTROL デザイン]**&#x200B;をクリックしてエクスペリエンスを編集します。

ホバー状態がJavaScriptに依存している場合は、**[!UICONTROL JavaScriptを無効にする]**&#x200B;が選択されていないことを確認してください。 JavaScriptに依存する要素を編集するには、Adobe Targetを有効にする必要があります。

使用可能な編集オプションについて詳しくは、[Visual Experience Composerのオプション &#x200B;](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)を参照してください。

## ページ読み込みを管理 {#manage-page-loading}

ページの読み込み中や読み込みに失敗した後も、一部の編集オプションを利用できます。 ページの読み込みをキャンセルして、待たずにこれらのオプションにアクセスすることもできます。

### ページの読み込み中またはページの読み込みに失敗した後にページを編集する {#loading}

ページの読み込みがVECで完了する前や、カスタムコードが機能しなくなったため、ページの読み込みに失敗した後に、いくつかの変更を行うことができます。

使用可能な編集オプションを使用して、次の操作を行います。

* カスタムコードの追加やエクスペリエンスの名前の変更など、簡単な変更を行います
* アクセスできなくなったページから既存のカスタムコードをコピーする
* VECで読み込めないページを簡単に編集する

ページの読み込み中または読み込みに失敗した後も、[!UICONTROL &#x200B; エクスペリエンス &#x200B;] パネル、[!UICONTROL &#x200B; コンポーネント &#x200B;] パネル、[!UICONTROL 設定] オプションにアクセスできます。

### VEC内のページの読み込みをキャンセル {#cancel-loading}

VECでのページ読み込みをキャンセルして、ページの読み込みが完了するのを待たずにアクティビティを編集します。

ページ読み込みのキャンセルは、次のような場合に便利です。

* 既存の修正を微調整する
* 1つ以上の既存の修正を削除
* カスタムコードの挿入または編集
* 誤って入力されたページ URLの修正
* VECにページを読み込む前に、JavaScriptを有効または無効にします
* [!UICONTROL &#x200B; ページ配信]条件にテンプレートテストルールを追加
* EEC経由またはiframe専用モードでページを読み込む際に、グローバルな[!UICONTROL Enhanced Experience Composer] （EEC）トグルを上書きする

ページの読み込みをキャンセルした後、ページの読み込みを待たずに、アクティビティ内のエクスペリエンスを切り替えることができます。 **[!UICONTROL 再読み込み]**&#x200B;をクリックして、ページをVECに再度表示します。

>[!IMPORTANT]
>
>ページの読み込みをキャンセルした後にカスタムコードを編集したり、その他の変更を加えたりする場合は、品質保証（QA）テストを実行して、変更が期待どおりに配信されていることを確認します。

ページの読み込みを停止するには、ページの読み込み中に&#x200B;**[!UICONTROL 読み込みをキャンセル]**&#x200B;をクリックします。 ページを再ロードしない限り、現在の編集セッション中も、このアクティビティのページはアンロードされたままになります。

「**[!UICONTROL 再読み込み]**」をクリックして、現在のアクティビティでのエクスペリエンスの管理を再開するか、新しい変更を追加します。
