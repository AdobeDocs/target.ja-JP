---
keywords: css セレクター;カスタムコード;コードエディター;モバイル Web エクスペリエンスエディター
description: Adobeの変更パネルを使用して、ページ  [!DNL Target]  変更を表示し、追加の変更（CSS セレクター、mbox、カスタムコード）を追加する方法を説明します。
title: ページにどのような変更を加えることができますか？
feature: Visual Experience Composer (VEC)
exl-id: 23456a4b-9457-4f05-989e-a7c39ce17cc2
source-git-commit: e458793e4d0110d97f3f5124cbe6e54520d3f0e9
workflow-type: tm+mt
source-wordcount: '2207'
ht-degree: 72%

---

# 変更

ページへの変更を表示し、追加の変更（CSS セレクター、mbox およびカスタムコード）を追加できる [!DNL Adobe Target] の [!UICONTROL Modifications] ページに関する情報です。

[!UICONTROL Modifications] ページには、Visual Experience Composer （VEC）でページに加えられたすべての変更が表示され、ページ上の各要素をクリックして（アクションを選択 [ 追加の変更を加えること ](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81) できます。 行った変更は、個別のアクションまたは要素として [!UICONTROL Modifications] ータリストに表示されます。 さらに、CSS セレクター、mbox、カスタムコードなどのタイプの変更を加えることもできます。

## 変更の概要 {#section_EE27E7572AA74397BBDED563B2B3D509}

[!UICONTROL Modifications] ページには、ページに加えられたすべての変更が VEC で表示されます。 行った変更は、個別のアクションまたは要素として [!UICONTROL Modifications] ータリストに表示されます。

![codeeditor_page_mods 画像 ](assets/codeeditor_page_mods.png)

変更ページを使用すると、VEC を使用してコンテンツの配信方法を設定するときに Target で選択されるセレクターに少し変更を加えることができます。コンテンツまたは HTML 属性を変更できます。コードを編集して、mbox 内に HTML オファーと同等のものを作成することもできます。

変更ページを使用すると、次のことをおこなえます。

* Visual Experience Composer でおこなったアクションの表示。

  ![codeeditor_viewchange 画像 ](assets/codeeditor_viewchange.png)

* 既存のアクションの編集。目的の変更にカーソルを合わせ、「**[!UICONTROL Edit]**」アイコンをクリックします。

  ![codeeditor_edit image](assets/codeeditor_edit.png)

  変更を加えます。

  ![codeeditor_changechange1 画像 ](assets/codeeditor_changechange1.png)

* 既存のアクションを削除します。 目的の変更にカーソルを合わせ、「**[!UICONTROL Delete]**」アイコンをクリックします。

  ![codeditor_delete image](assets/codeditor_delete.png)

* 新しい変更の追加。「**[!UICONTROL Add Modification]**」または「+」アイコンをクリックし、以下に説明するように変更を指定します。

  ![codeeditor_new image](assets/codeeditor_new.png)

  変更が 1 つ作成されたら、Target には、パネルの下部にある「変更を追加」ボタンの代わりに、変更パネルの上部に + アイコンが表示されることに注意してください。

* 変更パネルを Target UI の側辺に沿って垂直に、または下部へ水平にドッキングします。[!UICONTROL Dock] アイコンをクリックすると、2 つの設定を切り替えることができます。

  ![codeditor_dock 画像 ](assets/codeditor_dock.png)

  次の図に、画面の下部にドッキングされた変更パネルを示します。

  ![codeeditor_dock_bottom 画像 ](assets/codeeditor_dock_bottom.png)

## 変更の追加 {#section_C7ABCD5731A048CB8F90EDC31A32EDF9}

1. 選択したエクスペリエンスの [!UICONTROL Modifications] ページを表示するには、VEC で「**[!UICONTROL Modifications]**」アイコン（&lt;/>）をクリックします。

   ![codeeditor_icon_big image](assets/codeeditor_icon_big.png)

   >[!NOTE]
   >
   >フォームベースの Experience Composer で変更パネルを開くには、HTMLオ ファーを作成または編集します。詳しくは、[フォームベースの Experience Composer](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E) を参照してください。

   [!UICONTROL Modifications] ページが開き、画面が左側のビジュアルモードと右側の変更パネルに分割されます。 [!UICONTROL Dock] アイコンをクリックして、変更パネルを Target UI の横に垂直に、または下部に水平にドッキングします。 次の図のエクスペリエンス A は、これまで変更されたことがありません。

   ![codeeditor_page image](assets/codeeditor_page.png)

   エクスペリエンス B では、右側のエクスペリ [!UICONTROL Modifications] ンスパネルに以前の変更が表示されます。

   ![codeeditor_page_mods 画像 ](assets/codeeditor_page_mods.png)

1. 変更を追加するには：

   * エクスペリエンスに以前の変更がない場合は、右側のエクスペリ [!UICONTROL Modifications] ンスパネルの下部にある **[!UICONTROL Add Modification]** ボタンをクリックします。
   * エクスペリエンスに以前の変更がある場合は、右側のエクスペリ [!UICONTROL Modifications] ンスパネルの上部にある「+」アイコンをクリックします。

   次のような変更パネルが表示されます。

   ![codeeditor_page_mods_add image](assets/codeeditor_page_mods_add.png)

1. **[!UICONTROL Modifications Type]** ドロップダウンリストから、目的のタイプを選択します。

   | 変更タイプ | 詳細 |
   |--- |--- |
   | CSS セレクター | CSS 要素セレクターボックスで、変更する CSS 要素を指定し、アクションタイプ（「コンテンツを設定」または「属性を設定」）を選択して、必要な情報と目的のコンテンツを入力します。 |
   | mbox | mbox 名と目的のコンテンツを指定します。<p>**メモ**:at.js 2 を使用するページの VEC では、mbox がサポートされなくなりました。**。<p>回避策：<ul><li>at.js を使用する場合 2.*x*:mbox の変更ではなく CSS セレクターの変更を追加し、mbox が使用していたセレクターにコンテンツを追加します。 </li><li>フォームベースのアクティビティを使用する（mbox および at.js で機能 1.*x* と at.js 2 の両方について示しています。*x*）。</li><li>at.js 1 の使用&#x200B;*x* を VEC で使用します。</li></ul> |
   | カスタムコード | オプション名を指定し、必要に応じて「[!UICONTROL Add Code in the `<HEAD>` セクション &#x200B;]」チェックボックスを選択または選択解除して、カスタムコードを追加します。<p>[!UICONTROL Add Code in the `<HEAD>` Section] を選択すると、カスタムコードが `<head>` セクションに追加され、body または page-load イベントを待たずにその実行が実行されます。 `<script>` および  `<style>` の要素のみを追加します。`<div>` タグなどの要素を追加すると、残りの `<head>` 要素が `<body>` に表示される場合があります。at.js を使用している場合、すべてのオファーが非同期で配信されます。<p> [!UICONTROL Add Code in the `<HEAD>` Section] の選択を解除すると、カスタムコードは `<body>` タグの直後に実行されます。 すべてのコードを 1 つの `<div>` 内にラップして、DOM 構造を保持します。at.js を使用している場合、すべてのオファーが非同期で配信されます。<p>`<BODY>` のHTMLに `<SCRIPT>` と `<DIV>` が含まれる場合、`<DIV>` が `<BODY>` に追加され、`<SCRIPT>` が `<HEAD>` で実行されます。 また、外部ファイルを読み込む `<SCRIPT>` が `<HEAD>` に追加されます。<p>**メモ**：スクリプトは非同期で実行されます。 つまり、例えば `document.write` や類似のスクリプトメソッドは使用できません。<p>カスタムコードでは、非ビジュアルインターフェイスを使用して、VEC、フォームベースの Experience Composer、HTML オファーエディター内でアクションを表示および編集したり、新規で追加したりできます。パネルでは、エクスペリエンスのコードを見ながら、複雑なエクスペリエンスの構築、既存のエクスペリエンスの調整、問題のトラブルシューティングをおこなうことができます。<p>カスタムコードは、HTML、JavaScript および CSS の使用に慣れた上級ユーザー向けの機能です。コードビューでは、コードを変更して微調整したり、セレクターの問題を修正したりできます。新しいカスタムコードおよびアクションを追加することもできます。カスタムコードを複数追加し、オプションでそれぞれのカスタムコードに名前を付けることができます。<p>**メモ**：カスタムコードは現在、A/B およびエクスペリエンスのターゲット設定（XT）アクティビティでのみ使用できます。 オーバーレイの場合とリダイレクトオファーが適用されている場合、カスタムコードは無効になります。<p>カスタムコードでは、次のような操作をおこなうことができます。<ul><li>ページ上部で実行するカスタムの JavaScript、HTML または CSS の追加</li><li>変更後に VEC によって生成されるコードの表示または編集</li><li>セレクターに対する HTML コンテンツの設定（CSS セレクターのみ）</li><li>HTML 要素に対する属性の設定</li><li>リージョナル mbox に配信するオファーコンテンツの追加</li><li>DOM 準備完了時の置き換え（jQuery 使用）</li><li>DOM 準備完了時の置き換え（jQuery 不使用）（Internet Explorer 8 は非対応）</li><li>DOM ポーリングでの置き換え（「elementOnLoad」プラグイン使用）</li><li>カスタムリダイレクト</li></ul>カスタムコードには次の特長があります。<ul><li>わかりやすさを考慮した行番号</li><li>HTML オファーの構文の誤りを防ぐのに役立つ構文情報</li><li>複数のカスタムコードを作成し、オプションでそれぞれに名前を指定できる機能複数のカスタムコードを作成すると、今後のデバッグが容易になります。例えば、複数の変更をおこなう単一のカスタムコードを作成するのではなく、変更ごとに別個のカスタムコードを作成し、それぞれにわかりやすい名前を付けることができます。別個のカスタムコードにすることで、変更がモジュール化され、扱いやすくなります。アクティビティで複数のカスタムコードを実行する場合は、作成した順に実行されるとは限らないことに注意してください。</li></ul>変更パネルは、ビジュアルモードとコードモードの画面に分割されます。両方のモードが同期された状態になります。ビジュアルモードで変更をおこなうと、コードビューの対応する行が変更されます。同様に、コードビューで変更を確定するたびに、ビジュアルエクスペリエンスに変更が表示されます。コードビューで任意の行をクリックすると、ビジュアルページで対応する要素が選択されます。<p>カスタムコードでは、HTML、スクリプトおよびスタイルをサポートしています。有効な HTML コードまたはスクリプトを追加または編集できます。 |

1. 必要に応じて、さらに変更を加えます。

## カスタムコードの使用例 {#section_26CB3360097D400FB02E20AE5FDBA352}

**[!UICONTROL Custom Code]** パネルには、ページの読み込みの開始時に実行されるコードが含まれています。

`<head>` タグ内の JavaScript コードを実行できます。`<body>` タグが DOM に表示されるのを待たずに、コードが実行されます。

後続のビジュアルアクションのセレクターは、このタブで追加される HTML 要素に依存します。

カスタムコードパネルは、通常、ページの上部に JavaScript または CSS を追加するために使用されます。

![codeeditor_custom image](assets/codeeditor_custom.png)

「**[!UICONTROL Custom Code]**」タブを使用して、次の操作を行います。

* JavaScript のインラインでの使用、または外部 JavaScript ファイルへのリンク

  例えば、要素の色を変更するには、次のように入力します。

  ```javascript
  <script type="text/javascript"> 
  document.getElementById("element_id").style.color = "blue"; 
  </script> 
  ```

* インラインでのスタイルの設定、または外部スタイルシートへのリンク

  例えば、オーバーレイ要素のクラスを定義するには、次のように入力します。

  ```html
  <style> 
  .overlay 
  { position: absolute; top:0; left: 0; right: 0; bottom: 0; background: red; } 
  </style> 
  ```

* HTML スニペットを追加して新しい要素を定義

  例えば、上で定義した CSS クラスを使用してオーバーレイ `<div>` を作成するには、次の HTML スニペットを使用します。

  ```html
  <div class="overlay"></div>
  ```

* DOM 準備完了時の置き換え（jQuery 使用）

  JQuery を使用した次の例では、オファーの実行時に顧客の web サイトのページで jQuery が使用可能で [!DNL Target] ることを前提としています。

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  jQuery( document ).ready(function() { 
      jQuery("#default_content").html( "<span style='color:red'>Hello <strong>Again</strong></span>" ); 
      jQuery("#default_content").css("visibility","visible"); 
  }); 
  </script> 
  ```

* DOM 準備完了時の置き換え（jQuery 不使用）（Internet Explorer 8 は非対応）

  ```javascript
  <style>#default_content {visibility:hidden;}</style> 
  <script> 
  document.addEventListener("DOMContentLoaded", function(event) {  
      document.getElementById("default_content").innerHTML = "<span style='color:red'>Hello <strong>Again</strong></span>"; 
      document.getElementById("default_content").style.visibility="visible"; 
  }); 
  </script> 
  ```

* 既存のパラメーター、`s_tnt` パラメーター（Analytics への従来の統合）、リファラーパラメーターおよび mbox セッションを渡すカスタムのリダイレクト

  ```javascript
  <style type="text/css">body{display:none!important;}</style> 
  <script type="text/javascript"> 
   var qs='';window.location.search?qs=window.location.search+'&':qs='?'; 
   window.location.replace('//www.mywebsite.com/'+qs+'s_tnt=${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}&s_tntref='+encodeURIComponent(document.referrer)+'&mboxSession='+mboxFactoryDefault.getSessionId().getId()+''+window.location.hash+''); 
  </script> 
  ```

* カスタムコードで使用する Adobe Target エクスペリエンステンプレートを追加します。Target エクスペリエンステンプレートは、マーケティング担当者向けの一般的な使用例を実行するための設定可能な入力を備えたコーディング済みのサンプルです。これらのエクスペリエンステンプレートは、VEC またはフォームベースの Experience Composer を通じて一般的な使用例を実行するための出発点として開発者およびマーケティング担当者に無償で提供されます。使用例には、ライトボックス、カルーセル、カウントダウンなどがあります。

  詳しくは、[エクスペリエンステンプレート](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/experience-templates.md#concept_109BBD7EABC04DD39E6B7B1687786652)を参照してください。

## カスタムコードのベストプラクティス {#section_10DFFD9FB92A43C1BB444A45E0272B28}

**カスタムコードは、必ず 1 つの要素にまとめます。**

例：

```html
<div id="custom-code"> 
// My Code goes here 
</div>
```

変更が必要な場合は、このコンテナ内でおこないます。

カスタムコードが不要になった場合は、コンテナを空のままにし、削除しないようにします。コンテナを残しておくことで、他のエクスペリエンスの変更時にそのまま変更をおこなうことができます。

**コードエディターでのページに対する変更では、要素 ID「CDQID」を使用しないでください。**

Target では、Target で変更されたページ上の要素に対して値「CDQID」の新しい要素 ID を適用します。この ID は Target によって適用されるものなので、コードエディターでの変更や調整においてこの値を使用しないでください。

**カスタムコードスクリプトでは、document.write アクションを実行しないでください。**

スクリプトは、非同期で実行されます。`document.write` アクションは、非同期で実行されると、多くの場合ページ上の誤った場所に配置されます。カスタムコードで作成されたスクリプトで `document.write` を使用することはお勧めしません。

**要素を作成して変更した場合は、元の要素を削除しないでください。**

変更をおこなうたびに、変更パネルに新しい要素が作成されます。2 つ目の操作では、要素 1 を変更しているので、要素 1 を削除すると、2 つ目の操作で変更する対象となる要素がなくなるので、変更が動作しなくなります。詳しくは、以下の「トラブルシューティング」を参照してください。

**同じ URL をターゲットとする 2 つのアクティビティに対してカスタムコード機能を使用する場合は、注意が必要です。**

同じ URL をターゲットとする 2 つのアクティビティに対してカスタムコード機能を使用する場合、両方のアクティビティからページに対して JavaScript が挿入されます。Target は、配信されるコンテンツの順序を自動的に判断します。コードが、配置に依存しないようにしてください。コード内で競合が発生しないようにする必要があります。

## カスタムコードのトラブルシューティング {#section_6C965CBC31C348D7AA5B57B63DAB9E7F}

**`triggerView` を使用する場合、カスタムコードが実行されない。**

オプションとして `{page: false}` を使用して `triggerView()` が呼び出される場合、VEC のカスタムコードオファーは再レンダリングされません。

**ページの構造上の変更によってアクションを適用できなかったことを示す警告が表示されました。これはどういう意味ですか？** 

このメッセージは、アクティビティが最後に保存されてから、ページの構造が変更されたことを示します。

参照モードを使用して存在しないセレクターにアクセスしている可能性がります。警告メッセージに示されているように、コンテンツが想定どおりに表示されるようにするために、各エクスペリエンスを削除してから作成し直すことをお勧めします。

![code_editor_2 画像 ](assets/code_editor_2.png)

***要素を削除すると、「このアクションを削除すると、後続のアクションに影響する可能性があります」という警告が表示されます。」 これはどういう意味ですか？*** 

例えば、次の 2 つの操作をおこなったとします。

* クラスに要素 1 を追加
* 要素 1 の HTML を編集

変更をおこなうたびに、変更パネルに新しい要素が作成されます。2 つ目の操作では、要素 1 を変更しているので、要素 1 を削除すると、2 つ目の操作で変更する対象となる要素がなくなるので、変更が動作しなくなります。

つまり、テキストを持つ要素を追加し、別の操作でその要素を異なるテキストに編集した場合、変更パネルには、両方の操作が別々の要素として表示されます。要素を編集した場合は、作成した元の要素を変更した新しい要素が作成され、その新しい要素に編集したテキストが設定されます。その後、元の要素を削除すると、編集されたテキストは、編集された要素を見付けることができないので、表示されません。2 つ目の要素は要素のリストには引き続き含まれていますが、変更元の要素が存在しなくなっているので、ページ上での効果がなくなります。

***スクリプトで `document.write` を使用して作成した要素が、期待した場所に表示されません。***

スクリプトは、非同期で実行されます。`document.write` アクションは、非同期で実行されると、多くの場合ページ上の誤った場所に配置されます。アドビでは、カスタムコードで作成するスクリプト内で `document.write` を使用しないことをお勧めします。

***JavaScriptのカスタムコードにエラーが表示される。***

有効な JavaScript でないインライン JavaScript は、カスタムコードでエラーになります。

***カスタムコードの変更を元に戻すことができません。***

現在、変更パネルとカスタムコードでの編集操作および削除操作については、取り消しはサポートされていません。これらのいずれかの操作を取り消すと、VEC のエクスペリエンスの表示が、カスタムコードに表示されている実際のアクションと食い違っているように見える場合があります。ただし、カスタムコード内のアクションは正しい状態で、配信には影響はありません。これは、UI の問題です。エクスペリエンスを更新するには、保存してから再度開くか、または次のステップに移動して戻ります。これらのいずれかの操作をおこなうと、エクスペリエンスが再読み込みされ、期待どおりに表示されて、変更パネルのアクションとの整合性が保たれます。

**Internet Explorer 8 でカスタムコードが期待どおりの結果を返さない**

Target は、IE 8 をサポートしていません。
