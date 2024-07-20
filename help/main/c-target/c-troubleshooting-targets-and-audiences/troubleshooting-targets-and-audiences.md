---
keywords: トラブルシューティング、よくある質問、FAQ、FAQ、ターゲット、オーディエンス
description: Adobeアクティビティで使用されるエクスペリエンスのターゲティングとオーディエンスに関するよくある質問（FAQ）  [!DNL Target]  表示します。
title: ターゲットとオーディエンスに関する質問と回答
feature: Audiences
exl-id: f829bd4a-852a-4eb1-85d1-89e74c14b37e
source-git-commit: 6df7df69e54730d4c63bd17a33c12484e2bbdc92
workflow-type: tm+mt
source-wordcount: '955'
ht-degree: 56%

---

# ターゲットとオーディエンスに関する FAQ

エクスペリエンスのターゲット設定とオーディエンスに関するよくある質問（FAQ）のリストです。

## ターゲティング [!DNL Target]URL をどのように評価しますか？ {#url}

Target での URL の評価は、アクティビティの作成時にオーディエンス URL ターゲティングを使用するか、オーディエンスの作成時に URL ターゲティングを使用するかによって異なります。

次の URL について考えてみます。

`http://www.example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`

### オーディエンス URL のターゲティング

アクティビティの作成時にオーディエンス URL ターゲティングを適用するには、エクスペリエンス ページ（3 ステップのガイドによるワークフローの 1 つ）で、歯車アイコンをクリックし、「ページ配信」をクリックして、目的の URL を指定します。

![ ページ配信 URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/activity-url.png)

オーディエンス URL のターゲティングは、完全に一致する URL を検索します。 URL が一致する場合、Target はそれ以上のロジックを考慮しません。 上記の URL でアクティビティが `www.example.com` に実行されるように設定されている場合、オーディエンス URL ターゲティングはクエリに依存しないので、この URL は次の URL と一致します。

* `www.example.com?query=something`
* `www.example.com?query=anything`
* `www.example.com?query=nothing&qa=true&stuff=random&product=shoes&height=superTall`

URL でのオーディエンスのターゲティングに加えて、クエリに含めることができる特定の値を指定することもできます。

[!UICONTROL Template Rules] で追加されたオーディエンス URL ターゲティングと URL ターゲティングが、URL ターゲティングとして評価されます（以下の URL ターゲティングを参照）。

### URL ターゲティング {#url-targeting}

URL ターゲティングを適用するには、オーディエンスの作成時に「[!UICONTROL Add Rule]」をクリックし、「[!UICONTROL Site Pages]」をクリックします。最初のドロップダウンリスト（[!UICONTROL Current Page]、[!UICONTROL Previous Page] または [!UICONTROL Landing Page]）からオプションを選択し、2 番目のドロップダウンリストから「[!UICONTROL URL]」を選択してエバリュエーターを指定し、目的の URL を指定します。

![ サイトページ/現在のページ/URL](/help/main/c-target/c-troubleshooting-targets-and-audiences/assets/site-url.png)

URL ターゲティングは、URL を評価する一連のルールに変換します。

* URL = `example.com/path1/path2/path3?queryStringParam1=test123&queryStringParam2=test7`
* ドメイン = `example.com`
* パス = `path1/path2/path3`
* クエリ = `queryStringParam1=test123&queryStringParam2=test7`

## 複雑な URL 文字列を作成する場合、URL 全体 [!DNL Target] 評価しますか？

URL 文字列で同じパラメーター名を複数回使用する場合、HTTP は最初のパラメーター名を考慮し、後続の同じ名前のパラメーターは無視します。

例えば、次の URL 文字列の場合：

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438&Category=C000047`

`Category` パラメーターの最初のインスタンスが評価され、2 番目の `Category` パラメーターは無視されます。

ベストプラクティスは、次に示すように、1 つのカテゴリに複数の値を関連付けることです。

`https://www.adobe.com/SearchResults.aspx?sc=BM&fi=1&fr=1&ps=0&av=0&Category=C0010438,C000047`

## オーディエンスを構築する場合、[!DNL Target] ライブラリの下にある事前定義済みのオーディエンスが他のカテゴリに含まれるのはなぜですか？ {#section_9EBF5B0F9DF94168A15B92B905CCF7E0}

ターゲットライブラリカテゴリの事前設計されたオーディエンスは、従来のオーディエンスで、他のカテゴリに存在します。例として、従来のターゲットライブラリ／新しい訪問者のオーディエンスは、同等の訪問者プロファイル／新しい訪問者に更新されています。

パフォーマンスが向上しているので、より新しいオーディエンスを使用することをお勧めします。一部のお客様は、従来の事前構築されたオーディエンスを使用している可能性があるので、Target インターフェイスからは削除されていません。

## トラフィックはオーディエンス間でどのように分割されますか。 {#section_067EEFB956E7465CBF77EC86834470AB}

デフォルトでは、トラフィックはエクスペリエンス間で等しく分割されます。ただし、エクスペリエンスごとにパーセンテージのターゲットを指定できます。 この場合、乱数が生成され、その乱数を使用して、表示するエクスペリエンスが選択されます。結果の割合が指定したターゲットと完全に一致しないこともありますが、トラフィックが多いほど、エクスペリエンスがターゲットに近い割合で分割されます。

## ユーザーが、複数のオーディエンスを対象とする複数のエクスペリエンスを含んだアクティビティの資格を満たす場合、どのエクスペリエンスが表示されますか。 {#section_94A60B11212D48FD8AB0803C6C7E7253}

ユーザーは、アクティビティの [!UICONTROL Target] ページに表示される最初のエクスペリエンス/オーディエンスに該当します。

例えば、次の図では、Windows デバイスを使用するカリフォルニアのユーザーはエクスペリエンス A（Windows オーディエンス）とエクスペリエンス C（カリフォルニアオーディエンス）の両方の対象になります。ターゲットページではエクスペリエンス A の方がエクスペリエンス C より上に表示されるため、このユーザーにはエクスペリエンス A が表示されます。

![audiences_order 画像 ](assets/audiences_order.png)

## [!DNL Target]、Adobe Audience Manager（AAM）およびコアサービスのオーディエンスライブラリの同じオーディエンスの名前が異なるのはなぜですか？ {#section_F67E61A607B6444C8DAA4F99C3E95AED}

[!DNL Target] で名前を付けられたオーディエンスは一意ですが、[!DNL AAM] および [!DNL Audience Library] では、複数のオーディエンスに同じ名前を付けることができます（異なるフォルダーにある場合）。[!DNL AAM] または [!DNL Audience Library] のオーディエンスに対応するオーディエンス名が [!DNL Target] で検出された場合、[!DNL Target] はその名前に「#&lt;number>」を追加します。

例えば、「PC Users」（[!DNL AAM]）および「PC Users #1」（[!DNL Target]）というオーディエンスが表示されることがあります。

## オーディエンスの名前を変更できないのはなぜですか。 {#section_54E420556F534D20836E261E253D8B97}

「新しい訪問者」および「再訪問者」など、一部の Target オーディエンスは事前定義されています。これらの事前定義されたオーディエンスは、ユーザーが名前を変更することはできません。

## [!DNL Target] ユーザーインターフェイスにすべてのプロファイルパラメーターが表示されないのはなぜですか。 {#section_3CD947D15C984EE9AD19550220E0E8BD}

[!DNL Target] には、mbox 呼び出しごとに 50 個の独自のプロファイル属性という制限があります。50 個を超えるプロファイル属性を [!DNL Target] に渡す必要がある場合は、[!UICONTROL Profile Update] API メソッドを使用して渡すことができます。 詳しくは、Adobe Target API ドキュメントの [Profile Update](https://developers.adobetarget.com/api/#authentication-tokens) を参照してください。

## 訪問者に、提供されないはずの AP アクティビティのエクスペリエンスが表示されるのはなぜですか。 {#section_41CECEAE0881446A8D9F3B016857914B}

Automated Personalizationアクティビティは、セッションごとに評価されます。特定のエクスペリエンスに対する条件を満たしたアクティブなセッションがあり、そこに新しいオファーが追加されると、ユーザーには、以前まで表示されていたオファーとともに新しいコンテンツが表示されます。こうしたユーザーは、それまでに対象のエクスペリエンスの条件を満たしていたので、セッションの有効期間中は引き続きそのエクスペリエンスが表示されます。ページ訪問のたびにアクティビティを評価したい場合は、エクスペリエンスのターゲット設定（XT）のアクティビティタイプを使用してください。

## API を使用して作成されたオーディエンスに対して行われた変更が [!DNL Target] UI に反映されないのはなぜですか？ {#section_6BEB237CAC004A06A290F9644E5BF0FB}

オファーやプロファイルスクリプトとは異なり、Target Standard で作成されたオーディエンスに API で加えられた変更は、現時点では、Target UI には反映されません。

## 数値（浮動小数点数もサポートされます）を表す文字列は、数値と比較されます。{#strings-that-represent-numbers}

等号式の左と右の部分を数値に解析できる場合、2つの部分は文字列ではなく数値として比較されます。

次に例を示します。

| 値 | ターゲット設定条件 | 結果 |
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

&quot;4e-2&quot;は&quot;4e-2&quot;にのみ等しくなります。&quot;0.04&quot; と等しく&#x200B;*なりません*。
