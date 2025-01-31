---
keywords: visual experience composer;vec;wysiwyg
description: Adobe Targetでの Visual Experience Composer （VEC）の使用に関する基本を説明します。 VEC は、パーソナライズされたエクスペリエンスを簡単に作成できるWYSIWYG エディターです。
title: Visual Experience Composer （VEC）の使用方法
feature: Visual Experience Composer (VEC)
hide: true
hidefromtoc: true
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '1101'
ht-degree: 59%

---

# Visual Experience Composer（VEC）

[!DNL Adobe Target] での [!UICONTROL Visual Experience Composer] （VEC）の使用に関する情報です。

VEC は、サイトコンテキストのパーソナライズされたエクスペリエンスやオファーを簡単に作成およびテストできる、WYSIWYGのユーザーインターフェイスです。 Web ページ（またはオファー）またはモバイル Web ページのレイアウトやコンテンツをドラッグ&amp;ドロップ、入れ替えおよび変更することで、[!DNL Target] アクティビティのエクスペリエンスおよびオファーを作成できます。

VEC は [!DNL Adobe Target] の主要機能の 1 つです。VEC を使用すると、マーケターやデザイナーが視覚的なインターフェイスを使用してコンテンツを作成および変更できます。コードを直接編集することなく、多くのデザインの選択肢を作成できます。コンポーザーで利用可能な編集オプションを使用すれば、HTML および JavaScript の編集も可能です。

「Target **[!UICONTROL Administration]** / **[!UICONTROL Visual Experience Composer]**」タブで、デフォルトの [!UICONTROL Visual Experience Composer] URL を入力できます。

![ハイライトされた VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

この URL は、VEC を開いたときに、どこから開始するかを決定します。デフォルトを入力しないと、エディターを開いたときに空白ページが表示され、そこで URL を指定することになります。

>[!NOTE]
>
>[!DNL Firefox] などの特定のブラウザーでは、ページに混在したコンテンツが含まれている場合（例えば、安全なサイトの安全でないページ）、ページの VEC での表示がブロックされる場合があります。 ページが表示されない場合は、ブラウザーのアドレスバーで URL の横にあるアイコンをクリックし、「**[!UICONTROL Disable protection on this page]**」をクリックします。 この問題は、サイト訪問者へのページ表示に影響しません。

ページ上の iframe 内のコンテンツは、VEC では変更できません。iframe 内のコンテンツを編集するには、iframe ドキュメントが [!DNL Target] 有効になっていることを確認してから、VEC でその iframe URL を読み込みます。

[!UICONTROL Experiences] フレームのタブを使用すると、様々なオーディエンスや異なるエクスペリエンスで表示されるページを確認できます。 各エクスペリエンスの名前を指定できます。 例えば、ナビゲーションバーのホームリンクの場所をテストする場合は、ホームリンクが最初に表示されるエクスペリエンスに「ホームリンク」のような名前を付けて、リスト内でエクスペリエンスを識別しやすくすることができます。

>[!NOTE]
>
>ページの構造に加える変更が、そのページ上で作成されるアクティビティによって使用される場所に影響する場合は、エクスペリエンスの編集に問題が生じることがあります。VEC 外で場所を変更した場 [!DNL Target]、コンテンツが変更された場所を見つけることができない場合があります。

マウスポインターがページの周囲を移動すると、カーソルに従って状況依存型のボックスがページ上の要素をハイライトします。

<!--Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)-->

ハイライト表示された要素をクリックすると、その要素タイプで使用可能なオプションのメニューが表示されます。例えば、画像をクリックして **[!UICONTROL Change Image]** を選択すると、画像を別の画像に変更できます。 または、ボタンをクリックしてテキストの色を変更します。

「**[!UICONTROL Browse]**」をクリックして、プライマリページから使用できるページ（配送ページや買い物かごなど）に移動し、そのページの変更をテストすることもできます。 さらに、フライアウトメニューやミニ買い物かごなど、マウスポインターを置いたときに使用できるページ要素にアクセスすることもできます。ページへの参照が完了したら、「**[!UICONTROL Design]**」をクリックしてエクスペリエンスを編集します。 例えば、買い物かごのドロップダウンや画像のカルーセルのデザインを変更したい場合があります。

>[!NOTE]
>
>ホバー状態がJavaScriptに依存する場合は、**[!UICONTROL Disable JavaScript]** が選択されていないことを確認します。 JavaScript の要素を編集するには JavaScript が有効になっている必要があります。

VEC で利用可能なオプションについて詳しくは、[Visual Experience Composer オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)を参照してください。

ページの読み込み中（またはページの読み込みに失敗した後）に、ページでいくつかの変更を実行したり、VEC でページの読み込みをキャンセルしたりできます。詳しくは、次を参照してください。

* [ページの読み込み中または読み込みに失敗した後にページを編集します](#loading)
* [VEC 内のページの読み込みのキャンセル](#cancel-loading)

## ページの読み込み中または読み込みに失敗した後にページを編集します {#loading}

VEC でページが読み込まれる前や、ページを読み込めなかった場合（例えば、カスタムコードが動作しなくなった場合など）には、様々なアクションを実行できます。

VEC 内でページの読み込み中またはページの読み込みに失敗した後に、ページにアクセスしたり、ページを編集したりする理由：

* カスタムコードを追加したり、エクスペリエンスの名前を変更したりするなど、ページに簡単な変更を行う
* アクセスできなくなったページから既存のカスタムコードをコピーする
* VEC 内でページが読み込まれないことはわかっているが、それでも簡単な編集を行いたい

ページの読み込み（読み込みに失敗した後の読み込み）中は、[!UICONTROL Experiences] ースパネル、[!UICONTROL Modifications] ントロールパネルおよびエクスペリエンスの上部の設定（オーバーレイ、変更、設定など）すべてにアクセスできます。

## VEC 内のページの読み込みのキャンセル {#cancel-loading}

ページの読み込みを待たずに VEC 内でページの読み込みをキャンセルして、アクティビティの編集のロックを解除できます。この機能によって時間を節約し、VEC 内でページの読み込みを待たずに、簡単な編集やカスタムコードの挿入をより効率的に行うことができます。

VEC 内でページの読み込みをキャンセルする理由には、次のようなものがあります。

* 既存の変更に軽微な編集を行う
* 1 つ以上の既存の変更を削除する
* カスタムコードを挿入または編集する
* 正しくないページの URL を誤って入力した
* VEC でページを読み込む前に JavaScript を有効または無効にする
* ページ配信条件にテンプレートテストルールを追加する
* EEC または iframe のみを介したページの読み込みがページごとに異なる可能性がある場合、「グローバル拡張 Experience Composer（EEC）」切り替えを上書きする

VECで ページの読み込みをキャンセルした後、ページの読み込みを待たずに、アクティビティのエクスペリエンスを切り替えることができます。VEC 内のページを再度表示するには、「**[!UICONTROL Reload]**」ボタンをクリックする必要があります。

>[!IMPORTANT]
>
>VEC 内での読み込みをキャンセルすることを選択してカスタムコードを作成したり、変更を行ったりする場合は、コーディングまたは変更が正しく行われていることを確認する必要があります。適切な QA を実行して、カスタムコードの作成やその他の修正が期待どおりに行われていることを確認してください。

VEC 内のページの読み込みをキャンセルするには、ページの読み込み中に「**[!UICONTROL Cancel Loading]**」ボタンをクリックします。 現在の編集セッション中、このアクティビティのページは VEC に読み込まれません。

現在のアクティビティのエクスペリエンスの管理を続行したり、新しい変更を追加したりするには、「**[!UICONTROL Reload]** 定」ボタンをクリックする必要があります。
