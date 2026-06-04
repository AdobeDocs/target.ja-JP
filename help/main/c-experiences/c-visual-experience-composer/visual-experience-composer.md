---
keywords: visual experience composer;vec;wysiwyg
description: Adobe TargetでのVisual Experience Composer （VEC）の使用方法の基本について説明します。 VECは、パーソナライズされたエクスペリエンスを容易に構築できるWYSIWYGエディターです。
title: Visual Experience Composer （VEC）の使用方法を教えてください。
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 16fb7a1902ea76cab56a93fa141a32a3c6bc4467
workflow-type: tm+mt
source-wordcount: 1175
ht-degree: 47%

---

# [!UICONTROL Visual Experience Composer] （VEC）

[!DNL Adobe Target]の[!UICONTROL Visual Experience Composer] （VEC）は、コードを編集することなく、web サイトまたはモバイル web ページでパーソナライズされたエクスペリエンスを直接作成およびテストできるWYSIWYG エディターです。

>[!NOTE]
>
>[!DNL Target Standard/Premium] 25.2.1 （2025年2月17日（PT））リリースには、VECの更新バージョンが含まれています。 更新されたVECが以前のバージョンとどのように異なるかについて詳しくは、[Visual Experience Composerの変更](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md)を参照してください。 更新されたVECの様々なオプションの概要については、[Visual Experience Composerのオプション ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md)を参照してください。

VECでは、サイトコンテキストでパーソナライズされたエクスペリエンスとオファーを簡単に作成してテストできます。 Web ページ（またはオファー）またはモバイル Web ページのレイアウトやコンテンツをドラッグ＆ドロップ、入れ替え、変更することで、[!DNL Target] アクティビティのエクスペリエンスおよびオファーを作成できます。

VEC は [!DNL Target] の主要機能の 1 つです。 VEC を使用すると、マーケターやデザイナーが視覚的なインターフェイスを使用してコンテンツを作成および変更できます。 コードを直接編集することなく、多くのデザインの選択肢を作成できます。 コンポーザーで利用可能な編集オプションを使用すれば、HTML および JavaScript の編集も可能です。

[!DNL Target] **[!UICONTROL 管理]** > **[!UICONTROL Visual Experience Composer]** タブで、デフォルトの[!UICONTROL Visual Experience Composer] URLを入力できます。

この URL は、VEC を開いたときに、どこから開始するかを決定します。 デフォルトのURLを入力しない場合は、エディターを開いたときに空白のページから開始し、URLを指定できます。

![ハイライトされた VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

>[!NOTE]
>
>[!DNL Firefox]などの特定のブラウザーでは、ページに混在コンテンツが含まれている場合（例えば、安全なサイト内の安全でないページなど）、VECでのページの表示がブロックされる場合があります。 ページが表示されない場合は、ブラウザーのアドレスバーのURLの横にあるアイコンをクリックし、**[!UICONTROL このページの保護を無効にする]**&#x200B;をクリックします。 この問題は、サイト訪問者へのページ表示に影響しません。

ページ上の iframe 内のコンテンツは、VEC では変更できません。 iframe内のコンテンツを編集するには、iframe ドキュメントが[!DNL Target]対応であることを確認してから、そのiframe URLをVECに読み込みます。

[!UICONTROL  エクスペリエンス ] パネルのタブを使用すると、異なるオーディエンスや異なるエクスペリエンスで表示されるページを表示できます。 各エクスペリエンスに名前を付けることができます。 例えば、ナビゲーションバー内のホームリンクの場所をテストする場合、ホームリンクが最初に表示されるエクスペリエンスに名前を付けることができます。 例えば、「ホームリンク」を使用すると、リスト内のエクスペリエンスを識別しやすくなります。

>[!NOTE]
>
>ページの構造を変更すると、そのページで作成されたアクティビティで使用されている場所に影響を与え、エクスペリエンス編集で問題が発生する場合があります。 VEC以外で場所が変更された場合、[!DNL Target]はコンテンツが変更された場所を見つけられない可能性があります。

マウスポインターがページの周囲を移動すると、カーソルに従って状況依存型のボックスがページ上の要素をハイライトします。

<!--
Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)
-->

ハイライト表示された要素をクリックすると、その要素タイプで使用可能なオプションのメニューが表示されます。 例えば、画像をクリックし、**[!UICONTROL 画像を変更]**&#x200B;を選択して、画像を別の画像に変更できます。 または、ボタンをクリックしてテキストの色を変更します。

また、「**[!UICONTROL 参照]**」をクリックし、プライマリページから使用できる買い物ページや買い物かごなどのページに移動して、そのページの変更をテストすることもできます。 さらに、フライアウトメニューやミニカートなど、マウスポインターを置いたときに使用できるページ要素にアクセスすることもできます。 ページの閲覧が完了したら、**[!UICONTROL デザイン]**&#x200B;をクリックしてエクスペリエンスを編集します。 例えば、買い物かごのドロップダウンや画像のカルーセルのデザインを変更したい場合があります。

>[!NOTE]
>
>ホバー状態がJavaScriptに依存している場合は、**[!UICONTROL JavaScriptを無効にする]**&#x200B;が選択されていないことを確認してください。 JavaScript の要素を編集するには JavaScript が有効になっている必要があります。

VEC で利用可能なオプションについて詳しくは、[Visual Experience Composer オプション](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81)を参照してください。

ページの読み込み中（またはページの読み込みに失敗した後）に、ページでいくつかの変更を実行したり、VEC でページの読み込みをキャンセルしたりできます。 詳しくは、次を参照してください。

* [ページの読み込み中またはページの読み込みに失敗した後にページを編集する](#loading)
* [VEC内のページの読み込みをキャンセル](#cancel-loading)

## ページの読み込み中またはページの読み込みに失敗した後にページを編集する {#loading}

VEC でページが読み込まれる前や、ページを読み込めなかった場合（例えば、カスタムコードが動作しなくなった場合など）には、様々なアクションを実行できます。

VEC 内でページの読み込み中またはページの読み込みに失敗した後に、ページにアクセスしたり、ページを編集したりする理由：

* カスタムコードを追加したり、エクスペリエンスの名前を変更したりするなど、ページに簡単な変更を行う
* アクセスできなくなったページから既存のカスタムコードをコピーする
* VEC 内でページが読み込まれないことはわかっているが、それでも簡単な編集を行いたい

ページの読み込み（または読み込みに失敗した後）は、[!UICONTROL  エクスペリエンス ] レール、[!UICONTROL  コンポーネント ] レール、[!UICONTROL 設定] オプションにアクセスできます。

## VEC内のページの読み込みをキャンセル {#cancel-loading}

ページの読み込みを待たずに VEC 内でページの読み込みをキャンセルして、アクティビティの編集のロックを解除できます。 この機能によって時間を節約し、VEC 内でページの読み込みを待たずに、簡単な編集やカスタムコードの挿入をより効率的に行うことができます。

VEC 内でページの読み込みをキャンセルする理由には、次のようなものがあります。

* 既存の変更に軽微な編集を行う
* 1 つ以上の既存の変更を削除する
* カスタムコードを挿入または編集する
* 正しくないページの URL を誤って入力した
* VEC でページを読み込む前に JavaScript を有効または無効にする
* [!UICONTROL  ページ配信]条件にさらにテンプレートテストルールを追加する
* EECまたはiframe-only経由でページを読み込む際に、グローバルな[!UICONTROL Enhanced Experience Composer] （EEC）トグルを上書きする必要があります

VECでページの読み込みをキャンセルした場合、ページの読み込みを待たずに、アクティビティ内のエクスペリエンスを切り替えることができます。 VEC内のページを再度表示するには、**[!UICONTROL 再読み込み]** ボタンをクリックする必要があります。

>[!IMPORTANT]
>
>VEC 内での読み込みをキャンセルすることを選択してカスタムコードを作成したり、変更を行ったりする場合は、コーディングまたは変更が正しく行われていることを確認する必要があります。 適切な QA を実行して、カスタムコードの作成やその他の修正が期待どおりに行われていることを確認してください。

VEC内のページの読み込みをキャンセルするには、ページの読み込み中に「**[!UICONTROL 読み込みをキャンセル]**」ボタンをクリックします。 現在の編集セッション中、このアクティビティのページは VEC に読み込まれません。

現在のアクティビティでエクスペリエンスの管理を続行したり、新しい変更を追加したりするには、**[!UICONTROL 再読み込み]** ボタンをクリックする必要があります。
