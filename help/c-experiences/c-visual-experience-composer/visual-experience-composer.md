---
description: Visual Experience Composer（VEC）の使用に関する情報です。
seo-description: Adobe Target での Visual Experience Composer（VEC）の使用に関する情報です。
seo-title: Adobe Target Visual Experience Composer（VEC）
title: Visual Experience Composer（VEC）
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Visual Experience Composer（VEC）{#visual-experience-composer-vec}

Visual Experience Composer（VEC）の使用に関する情報です。

VECは、主な機能の1つ [!DNL Adobe Target]です。VECは、マーケターやデザイナーが視覚的なインターフェイスを使用してコンテンツを作成および変更できるエディターです。コードを直接編集することなく、多くのデザインの選択肢を作成できます。コンポーザーで利用可能な編集オプションを使用すれば、HTML および JavaScript の編集も可能です。

Target の **[!UICONTROL セットアップ]**／**[!UICONTROL 環境設定]**タブで、デフォルト Visual Experience Composer URL を入力できます。

![デフォルトのVEC URL設定](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

このURLは、VECを開いたときに開始する場所を決定します。デフォルトを入力しないと、エディターを開いたときに空白ページが表示され、そこで URL を指定することになります。

>[!NOTE]
>
>Firefoxなどの一部のブラウザーでは、ページに混合コンテンツが含まれている場合（セキュアなサイトの非セキュアページなど）、VECにページが表示されないことがあります。ページが表示されない場合は、ブラウザーのアドレスバーのURLの横にあるアイコンをクリックし、「このページの保護 **[!UICONTROL を無効にする」をクリック]**します。この問題は、サイト訪問者へのページ表示に影響しません。

ページ上のiframe内のコンテンツは、VECでは変更できません。iframe内のコンテンツを編集するには、iframeドキュメントがTarget対応であることを確認し、そのiframe URLをVECで読み込みます。

ページ上部にあるドロップダウンメニューを使用して、異なるオーディエンスに表示されるページ、または異なるエクスペリエンスで表示されるページを確認できます。2 つ目のドロップダウンリストでは、各エクスペリエンスの名前を指定できます。例えば、ナビゲーションバーのホームリンクの場所をテストする場合は、ホームリンクが最初に表示されるエクスペリエンスに「ホームリンク」のような名前を付けて、リスト内でエクスペリエンスを識別しやすくすることができます。

>[!NOTE]
>
>ページの構造に加える変更が、そのページ上で作成されるアクティビティによって使用される場所に影響する場合は、エクスペリエンスの編集に問題が生じることがあります。場所がVEC以外の場所に変更された場合、Targetはコンテンツが変更された場所を見つけることができない可能性があります。

マウスポインターがページの周囲を移動すると、カーソルに従って状況依存型のボックスがページ上の要素をハイライトします。

![VECハイライト](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

ハイライトの表示方法を変更するには **[!UICONTROL 、オーバーレイ]** アイコンをクリックします。例えば、画像、リンク、地域mbox、変更またはJavaScriptのみを強調表示できます。ハイライトの色は変更できます。別々の要素タイプをハイライトする際に使用する、塗りの色とタイプも指定できます。

![オーバーレイ設定の変更](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

ハイライトされている要素をクリックして、その要素タイプで使用できるオプションのメニューを表示したり、 **[!UICONTROL 編集/テキスト/HTML]** を選択してテキストを変更したり、ボタンをクリックして背景色を変更したりできます。ページ左上のボタンを使用すると、オーバーレイのオンとオフが切り替えられます。

また、「**[!UICONTROL 参照]**」をクリックし、プライマリページから使用できる買い物ページや買い物かごなどのページに移動して、そのページの変更をテストすることもできます。さらに、フライアウトメニューやミニカートなど、マウスポインターを置いたときに使用できるページ要素にアクセスすることもできます。ページの参照が終了したら、「**[!UICONTROL 構成]」をクリックしてエクスペリエンスを編集します。**例えば、買い物かごのドロップダウンや画像のカルーセルのデザインを変更したい場合があります。

>[!NOTE]
>
>ホバーの状態が JavaScript に依存する場合は、「**[!UICONTROL JavaScript を無効にする]**」が選択されていないことを確認します。JavaScript の要素を編集するには JavaScript が有効になっている必要があります。

VECで使用できるオプションについて詳しくは [、Visual Experience Composerのオプション](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)を参照してください。

ページの読み込み中（またはページの読み込みに失敗した後）に、ページにいくつかの変更を実行したり、VECでページの読み込みをキャンセルしたりできます。詳しくは、次を参照してください。

* [ページの読み込み中またはページの読み込みに失敗した後のページの編集](#loading)
* [VEC内でのページの読み込みをキャンセル](#cancel-loading)

## ページの読み込み中またはページの読み込みに失敗した後のページの編集 {#loading}

VEC でページがロードされる前や、ページを読み込めなかった場合（例えば、カスタムコードが動作しなくなった場合など）には、様々なアクションを実行できます。

VEC内で読み込み中または読み込みに失敗したときに、ページにアクセスしたり編集したりする場合があります。

* ページに簡単な変更を加えて、カスタムコードを追加したり、エクスペリエンスの名前を変更したりする
* アクセスできなくなったページから既存のカスタムコードをコピーする
* ページがVEC内で読み込まれないことがわかっていますが、簡単な編集を行いたいと思います

ページ読み込み（または読み込みに失敗した後）、 [!UICONTROL エクスペリエンス] パネル、 [!UICONTROL 変更] パネル、エクスペリエンス上部の設定（オーバーレイ、変更、設定など）はすべてアクセスできます。

次の図は、ページの読み込み中にカスタムコードを挿入したり、その他のアクションを実行したりすることを示しています。

![ページロード](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## VEC内でのページの読み込みをキャンセル {#cancel-loading}

VEC内のページの読み込みをキャンセルして、ページの読み込みを待たずにアクティビティのロックを解除できます。この機能によって時間が節約され、VEC内でページの読み込みを待たずに、簡単な編集やカスタムコードの挿入をより効率的に行うことができます。

VEC内でページの読み込みをキャンセルする理由には、次のようなものがあります。

* 既存の変更に小さな編集を加える
* 1つ以上の既存の変更を削除したい場合
* カスタムコードを挿入または編集したい
* ページの誤ったURLを誤って入力した
* VECでページを読み込む前にJavaScriptを有効または無効にしたい
* ページ配信条件にテンプレートテストルールを追加する場合
* EECまたはiframeのみのページを経由してページを読み込むときに、グローバル拡張Experience Composer（EEC）の切り替えによってページがページに変わる可能性がある

VECでページの読み込みをキャンセルした後、ページの読み込みを待たずに、アクティビティのエクスペリエンスを切り替えることができます。VEC内のページを再度表示するには **[!UICONTOL 、「リロード」]** ボタンをクリックする必要があります。

>[!IMPORTANT]
>
>VEC内での読み込みをキャンセルすることを選択してカスタムコードまたは変更を行う場合は、コーディングまたは変更が正しく行われていることを確認する必要があります。適切なQAを実行して、カスタムコードおよびその他の修正が期待どおりに配信されることを確認してください。

VEC内でページの読み込みをキャンセルするには、ページの読み込み中に「読み込み **[!UICONTROL ]** をキャンセル」ボタンをクリックします。現在の編集セッション中に、このアクティビティ用のページがVECに読み込まれません。

![読み込みをキャンセルボタン](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

現在のアクティビティでエクスペリエンスの管理を継続したり、新しい変更を追加したりするには、 **[!UICONTROL 「リロード」]** ボタンをクリックする必要があります。

![リロードボタン](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>この機能に関する既知の問題は、次回のリリースで修正される予定です。詳しくは [、既知の問題と解決された問題](/help/r-release-notes/known-issues-resolved-issues.md#cancel) ページの&quot;VEC内のページの読み込みをキャンセルする」を参照してください。

## トレーニングビデオ

以下のビデオには、この記事で説明されている概念に関する詳細が収録されています。

### Visual Experience Composer（7:17）

このビデオでは、Visual Experience Composer のオプションの使用に関する情報を提供しています。

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Visual Experience Composer（1／2）（7：17）

* ページのコンテンツの変更
* ページのレイアウトの変更

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Visual Experience Composer（2／2）（7：29）

* エクスペリエンスの名前の変更と複製
* リダイレクトエクスペリエンスの作成
* 単一の URL または URL のグループに対するアクティビティのターゲット化
* 複数ページのアクティビティの作成
* レスポンシブ Web サイト用のエクスペリエンスのプレビューおよび構築
* オーバーレイを使用した要素のタイプのハイライト

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### Office hours: Visual Experience Composer

このビデオは、アドビカスタマーケアチーム主導による取り組みの 1 つである「[Office Hours](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)」の録画です。

* VEC の仕組み
* VEC で一般的な問題を回避する方法
* VEC で使用できる回避策

>[!VIDEO](https://video.tv.adobe.com/v/20784/)