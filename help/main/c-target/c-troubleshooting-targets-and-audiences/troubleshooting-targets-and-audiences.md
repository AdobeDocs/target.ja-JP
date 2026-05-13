---
keywords: トラブルシューティング、よくある質問、FAQ、FAQ、ターゲット、オーディエンス
description: Adobe [!DNL Target]  アクティビティで使用されるエクスペリエンスのターゲティングとオーディエンスに関するよくある質問（FAQ）を表示します。
title: ターゲットとオーディエンスに関する質問と回答はどこにありますか？
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
TQID: https://experienceleague.adobe.com/WI8A9wqYpjiCCUABg5cBxJ92WwFLYN7qM-0DeYkrxOk
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 982
ht-degree: 52%

---

# ターゲットとオーディエンスに関する FAQ

エクスペリエンスのターゲット設定とオーディエンスに関するよくある質問（FAQ）のリストです。

## [!DNL Target]はターゲティングでURLをどのように評価しますか？ {#url}

Targetでは、アクティビティの作成時にオーディエンス URL ターゲティングを使用するか、オーディエンスの作成時にURL ターゲティングを使用するかによって、URLの評価が異なります。

次のURLを検討します。

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### オーディエンス URL ターゲティング

アクティビティの作成中にオーディエンス URL ターゲティングを適用するには、**[!UICONTROL Experiences]** ページ （3段階のガイド付きワークフローの1つ）で、**[!UICONTROL Configure]** アイコン （![設定アイコン &#x200B;](/help/main/assets/icons/Setting.svg)）をクリックし、**[!UICONTROL Page Delivery]**&#x200B;をクリックしてから、目的のURLを指定します。

![&#x200B; ページ配信URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

オーディエンス URL ターゲティングでは、URLが完全に一致する必要があります。 URLが一致する場合、Targetはそれ以上のロジックを考慮しません。 上記のURLでは、アクティビティが`www.example.com`に対して実行されるように設定されている場合、オーディエンス URL ターゲティングはクエリに依存しないため、URLは次のURLと一致します。

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

URLでのオーディエンスターゲティング以外に、クエリに含めることができる特定の値を指定することもできます。

[!UICONTROL Template Rules]を介して追加されたオーディエンス URL ターゲティングとURL ターゲティングは、URL ターゲティングとして評価されます（以下のURL ターゲティングを参照）。

### URL ターゲティング {#url-targeting}

URL ターゲティングを適用するには、オーディエンスを作成する際に、**[!UICONTROL Site Pages]**&#x200B;をクリックして[!UICONTROL Create Audiences] ペインにドロップし、**[!UICONTROL Site Pages]**&#x200B;をクリックし、最初のドロップダウンリスト（[!UICONTROL Current Page]、[!UICONTROL Previous Page]または[!UICONTROL Landing Page]）からオプションを選択し、2番目のドロップダウンリストから[!UICONTROL URL]を選択し、エバリュエーターを指定してから、目的のURLを指定します。

![&#x200B; サイトページ >現在のページ > URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

URL ターゲティングは、URLを評価する一連のルールに変換します。

* URL = `example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`
* ドメイン = `example.com`
* パス = `path1/path2/path3`
* クエリ = `queryStringParam1=test123&queryStringParam2=test7`

## 複雑なURL文字列を作成する場合、[!DNL Target]はURL全体を評価しますか？

URL文字列で同じパラメーター名を複数使用する場合、HTTPは最初のパラメーター名を考慮し、同じ名前の後続のパラメーターを無視します。

例えば、次のURL文字列で指定します。

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

`Category` パラメーターの最初のインスタンスが評価され、2番目の`Category` パラメーターは無視されます。

以下に示すように、1つのカテゴリに複数の値を関連付けることがベストプラクティスです。

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## オーディエンスを構築する際に、[!DNL Target] ライブラリの下にある事前定義済みのオーディエンスが他のカテゴリに見つかるのはなぜですか？ {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

ターゲットライブラリカテゴリの事前設計されたオーディエンスは、従来のオーディエンスで、他のカテゴリに存在します。 例として、従来のターゲットライブラリ／新しい訪問者のオーディエンスは、同等の訪問者プロファイル／新しい訪問者に更新されています。

パフォーマンスが向上しているので、より新しいオーディエンスを使用することをお勧めします。 一部のお客様は、従来の事前構築されたオーディエンスを使用している可能性があるので、Target インターフェイスからは削除されていません。

## トラフィックはオーディエンス間でどのように分割されますか。 {#section_067EEFB956E7465CBF77EC86834470AB}

デフォルトでは、トラフィックはエクスペリエンス間で等しく分割されます。 ただし、各エクスペリエンスの目標の割合を指定できます。 この場合、乱数が生成され、その乱数を使用して、表示するエクスペリエンスが選択されます。 結果の割合が指定したターゲットと完全に一致しないこともありますが、トラフィックが多いほど、エクスペリエンスがターゲットに近い割合で分割されます。

## ユーザーが、複数のオーディエンスを対象とする複数のエクスペリエンスを含んだアクティビティの資格を満たす場合、どのエクスペリエンスが表示されますか。 {#section_94A60B11212D48FD8AB0803C6C7E7253}

ユーザーは、アクティビティの[!UICONTROL Target] ページに表示される最初のエクスペリエンス/オーディエンスに適格です。

例えば、エクスペリエンス/オーディエンスがWindowsをエクスペリエンス A、iOSをエクスペリエンス B、カリフォルニア州をエクスペリエンス Cとしてリストしているとします。 Windows デバイスを使用しているカリフォルニア州のユーザーは、Experience A （Windows オーディエンス）とExperience C （カリフォルニア州オーディエンス）の両方の対象となります。 ターゲットページではエクスペリエンス A の方がエクスペリエンス C より上に表示されるため、このユーザーにはエクスペリエンス A が表示されます。

## コアサービスの[!DNL Target]、Adobe Audience Manager （AAM）、およびAudience Libraryで同じオーディエンスの名前が異なるのはなぜですか？ {#section_F67E61A607B6444C8DAA4F99C3E95AED}

[!DNL Target] で名前を付けられたオーディエンスは一意ですが、[!DNL AAM] および [!DNL Audience Library] では、複数のオーディエンスに同じ名前を付けることができます（異なるフォルダーにある場合）。[!DNL AAM] または [!DNL Audience Library] のオーディエンスに対応するオーディエンス名が [!DNL Target] で検出された場合、[!DNL Target] はその名前に「#&lt;number>」を追加します。

例えば、「PC Users」（[!DNL AAM]）および「PC Users #1」（[!DNL Target]）というオーディエンスが表示されることがあります。

## オーディエンスの名前を変更できないのはなぜですか。 {#section_54E420556F534D20836E261E253D8B97}

「新しい訪問者」および「再訪問者」など、一部の Target オーディエンスは事前定義されています。 これらの事前定義されたオーディエンスは、ユーザーが名前を変更することはできません。

## [!DNL Target] ユーザーインターフェイスにすべてのプロファイル パラメーターが表示されないのはなぜですか？ {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] には、mbox 呼び出しごとに 50 個の独自のプロファイル属性という制限があります。 50を超えるプロファイル属性を[!DNL Target]に渡す必要がある場合は、[!UICONTROL Profile Update] API メソッドを使用して渡すことができます。 詳しくは、Adobe Target API ドキュメントの [Profile Update](https://developers.adobetarget.com/api/#authentication-tokens) を参照してください。

## 訪問者に、提供されないはずの AP アクティビティのエクスペリエンスが表示されるのはなぜですか。 {#section_41CECEAE0881446A8D9F3B016857914B}

Automated Personalizationアクティビティは、セッションごとに評価されます。 特定のエクスペリエンスに対する条件を満たしたアクティブなセッションがあり、そこに新しいオファーが追加されると、ユーザーには、以前まで表示されていたオファーとともに新しいコンテンツが表示されます。 こうしたユーザーは、それまでに対象のエクスペリエンスの条件を満たしていたので、セッションの有効期間中は引き続きそのエクスペリエンスが表示されます。 ページ訪問のたびにアクティビティを評価したい場合は、エクスペリエンスのターゲット設定（XT）のアクティビティタイプを使用してください。

## APIを介して作成されたオーディエンスに対して行われた変更が[!DNL Target] UIに反映されないのはなぜですか？ {#section_6BEB237CAC004A06A290F9644E5BF0FB}

オファーやプロファイルスクリプトとは異なり、Target Standard で作成されたオーディエンスに API で加えられた変更は、現時点では、Target UI には反映されません。

## 数値（浮動小数点数もサポートされます）を表す文字列は、数値と比較されます。{#strings-that-represent-numbers}

等号式の左と右の部分を数値に解析できる場合、2つの部分は文字列ではなく数値として比較されます。

次に例を示します。

| 値 | ターゲティング条件 | 結果 |
| --- | --- | --- |
| 1.0 | equals1 | true |
| 1 | equalSignoreCase1.0 | true |
| 1.230 | equals1 | true |
| 1.500 | equals1.5 | true |
| 1.200 | が2より小さい | true |
| 2 | が3.0より大きい | false |
| 045 | equals45 | true |

科学的表記法で記述された数値は、常に文字列として比較されます。

例：

&quot;4e-2&quot;は&quot;4e-2&quot;にのみ等しくなります。 &quot;0.04&quot; と等しく&#x200B;*なりません*。
