---
keywords: ランダムフォレスト；デシジョンツリー；ap;Automated Personalization
description: '[!UICONTROL Automated Personalization] （AP）  [!DNL Adobe Target]  よび [!UICONTROL Auto-Target] アクティビティの両方でランダムフォレストアルゴリズムを使用する方法を説明します。'
title: ランダムフォ  [!DNL Target]  レストアルゴリズムの使用方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1413'
ht-degree: 44%

---

# ランダムフォレストアルゴリズム

（AP）と [!DNL Auto-Target] の両方のアクティビティで使用される主なパーソナライゼーションアルゴリズムは、ランダムフォレストです。 ランダムフォレストなどのアンサンブル手法では、複数の学習アルゴリズムを使用して、構成学習アルゴリズムのいずれかから得られるよりも優れた予測パフォーマンスを得ます。 [!UICONTROL Automated Personalization] and [!UICONTROL Auto-Target] のランダムフォレストアルゴリズムは、トレーニング時に多数のデシジョンツリーを構築して機能する分類または回帰手法です。

統計学の観点から見ると、結果の予測に使用される単一の回帰モデルが思い浮かぶかもしれません。データサイエンスの最新の調査では、同一のデータセットから複数のモデルが構築され、効果的に組み合わせられる「アンサンブル手法」の方が、単一のモデルだけで予測する場合よりも結果が優れていることが示されています。

ランダムフォレストアルゴリズムは、[!UICONTROL Automated Personalization] アクティビティと [!UICONTROL Auto-Target] アクティビティで使用される、パーソナライゼーションアルゴリズムの基礎となる重要な要素です。 ランダムフォレストは、何百もの決定ツリーを組み合わせて、1 つのツリーが単独で作るよりも優れた予測を得ます。

## デシジョンツリーとは {#section_7F5865D8064447F4856FED426243FDAC}

デシジョンツリーの目標は、システムが学習できるすべての使用可能な訪問データを分類し、そのデータをグループ化することです。これにより、目標指標に関して、各グループ内の訪問は可能な限り類似するようになります。 ただし、グループ間では、訪問回数は、目標指標（コンバージョン率など）に関してできるだけ異なります。 デシジョンツリーは、トレーニングセット内の様々な変数を調べて、相互排他的で包括的（MECE）な方法でデータをこれらのグループ（または「リーフ」）に分割して、この目標を最大化する方法を決定します。

簡単な例で、2 つの入力変数があるとします。

* 性別（値は男性と女性の 2 つ）
* 郵便番号（小さなデータセット内の 5 つの値（11111、22222、33333、44444、55555）

目標指標がコンバージョンの場合、訪問データのコンバージョン率の変動量が最も大きいのは、2 つの変数のうちどちらであるかをツリーがまず判断します。

郵便番号が最も予測的だとします。この変数がデシジョンツリーの最初の「ブランチ」を形成します。続いて、訪問データをどう分割するかを判断します。各グループ内のレコードのコンバージョン率はできる限り差異が小さく、各グループ間のコンバージョン率はできる限り差異が大きくなるようにするといった具合です。この例では、11111、22222、33333 が 1 つの分割で、44444、55555 が 2 番目の分割であるとします。

このアクションにより、デシジョンツリーの最初のレイヤーが次のように表示されます。

![decsion_tree_1 画像 ](assets/decsion_tree_1.png)

デシジョンツリーでは、「最も予測可能な変数は何か」という質問があります。 この例では、変数は 2 つしかないので、答えは明らかに性別です。 ツリーは、データを（各分岐内で *分割するための同様の演習を完了するよ* になります。 まず、11111、22222、33333 のブランチを見てみましょう。これらの郵便番号で、男性と女性でコンバージョン率に差異がある場合は、リーフは男性と女性の 2 つになり、このブランチの処理はそれで完了します。他のブランチ、44444 と 55555 では、女性と男性のコンバージョン方法に統計的な違いはないと仮定します。 この場合、1 つ目のブランチが最後の分割となります。

例の結果、次のツリーになります。

![decsion_tree_2 画像 ](assets/decsion_tree_2.png)

## ランダムフォレストでは、デシジョンツリーをどのように使用しますか？ {#section_536C105EF9F540C096D60450CAC6F627}

デシジョンツリーは効果的な統計ツールになりますが、デメリットもあります。最も大きなデメリットは、データの「オーバーフィッティング」が生じ、1 つのデシジョンツリーで、最初のデシジョンツリーの構築に使用されていない将来のデータの予測精度が悪くなる場合があるという点です。これは、統計学習における[バイアス／バリアンストレードオフ](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff)と呼ばれる問題です。ランダムな森は、この過剰な課題を克服するのに役立ちます。 ランダムフォレストは簡単に言うと、同一のデータセットを基に、わずかに違う形で構築されたデシジョンツリーの集合で、「投票」によって単一のデシジョンツリーよりも優れたモデルを生成します。ツリーは、置き換え後の訪問レコードのサブセット（バギングと呼ばれます）をランダムに選択することと、属性のサブセットをランダムに選択することによって構築されます。これにより、フォレストは少し異なるデシジョンツリーで構成されます。 この手法では、ランダムフォレストに構築されたデシジョンツリーにわずかなバリエーションが生まれます。この適度な量のバリエーションを追加することで、アルゴリズムの予測精度が高まります。

## [!DNL Target] のパーソナライゼーションアルゴリズムでは、ランダムフォレストをどのように使用しますか。 {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### モデルの構築方法

次の図は、[!UICONTROL Auto-Target] と [!UICONTROL Automated Personalization] のアクティビティでモデルがどのように構築されるかを示したものです。

![random_forest_flow 画像 ](assets/random_forest_flow.png){width="650" zoomable="yes"}

1. Target は、エクスペリエンスやオファーをランダムに提供しながら、訪問者のデータを収集します
1. [!DNL Target] が大量のデータにヒットした後、[!DNL Target] は機能エンジニアリングを実行します
1. [!DNL Target] は、エクスペリエンスまたはオファーごとにランダムフォレスト モデルを作成します
1. モデル [!DNL Target] しきい値の品質スコアを満たしているかどうかを確認します
1. [!DNL Target] がモデルを実稼動環境にプッシュして、今後のトラフィックをパーソナライズします

[!DNL Target] は、自動的に収集されるデータと、ユーザーから提供されるカスタムデータを使用して、パーソナライゼーションアルゴリズムを構築します。 このモデルによって、訪問者に表示する最適なエクスペリエンスやオファーが予測されます。通常、エクスペリエンス（[!UICONTROL Auto-Target] アクティビティの場合）またはオファー（[!UICONTROL Automated Personalization] アクティビティの場合）ごとに 1 つのモデルが構築されます。 次に、最も高 [!DNL Target] 予測成功指標（コンバージョン率など）を生成するエクスペリエンスまたはオファーが表示されます。 これらのモデルは、予測に使用する前に、ランダムに割り当てられた訪問を対象にトレーニングをおこなう必要があります。そのため、アクティビティが開始されると、パーソナライゼーションアルゴリズムの準備が整うまで、パーソナライズ対象のグループに入っている訪問者にも複数のエクスペリエンスまたはオファーが配信されます。

各モデルは、アクティビティで使用される前に、訪問者の行動の予測に適していることを確認するために、検証する必要があります。 モデルは、カーブの下の領域（AUC）に基づいて検証されます。 検証が必要なため、パーソナライズされたエクスペリエンスの提供をモデルが開始する正確な時間は、データの詳細に依存します。 トラフィックのプランニングの観点からの目安としては、モデルが有効になるまでには、最低限のコンバージョン数が必要になるのが一般的です。

エクスペリエンスまたはオファーのモデルが有効になると、エクスペリエンスまたはオファー名の左にある時計のアイコンが緑色のチェックボックスに変わります。少なくとも 2 つのエクスペリエンスまたはオファーに有効なモデルがある場合、一部の訪問はパーソナライズされ始めます。

### 機能変換

データはパーソナライゼーションアルゴリズムに送られる前に、特徴変換がおこなわれます。特徴変換は、パーソナライゼーションモデルで使用するために、トレーニングレコードの収集データを準備する処理です。

特徴変換は属性のタイプによって異なります。属性（データサイエンティストは「特徴」と呼ぶこともあります）は次の 2 種類に大別されます。

* **分類：**&#x200B;分類特徴はカウントできませんが、様々なグループに分類できます。分類特徴には、国、性別、郵便番号などがあります。
* **数値：**&#x200B;数値特徴は測定やカウントが可能で、年齢や収入などがあります。

分類特徴の場合、可能なすべての特徴のセットが保持され、尤度変換を使用してデータサイズが低減されます。数値特性の場合、再スケールによって、機能がボード全体で同等になります。

### マルチアームバンディットによる学習とパーソナライズのバランスを取る

[!DNL Target] では、トラフィックをパーソナライズするためにパーソナライゼーションモデルを構築したので、今後の訪問者に対しては、明確なトレードオフが存在することになります。 現在のモデルに基づいてすべてのトラフィックをパーソナライズする必要があるか、ランダムにオファーを提供して新しい訪問者から引き続き学習する必要があるか。 パーソナライゼーションアルゴリズムによって訪問者に関する新たなトレンドを見つけ出すための学習を常におこないながら、トラフィックの大部分をパーソナライズできれば効果的です。

マルチアームバンディットは、[!DNL Target] がこの目標を達成するのにどのように役立つかです。 マルチアームバンディットでは、モデルは常にトラフィックのごく一部を「消費」して、アクティビティ学習の全期間を通じて学習を継続し、それまでに学習したトレンドの乱用を防止します。

データサイエンスの世界ではマルチアームバンディット問題は探検と搾取のジレンマの典型的な例ですそれぞれの未知の報酬確率を持つワンアームバンディットのコレクションが与えられます 重要なのは、プレーの成功率が最も高く、受け取られる報酬の合計が最大となるアームを生む戦略を開発することです。オンラインモデルが構築された後のオンラインスコアリングのシステムでは、マルチアームバンディットが使用されます。 このプロセスは、探索中のオンライン学習に役立ちます。 現在のマルチアームアルゴリズムは epsilon （ε）貪欲なアルゴリズムです。 このアルゴリズムでは、確率 1- ε の場合に、最適なアームが選択され、確率 ε の場合は、その他のアームがランダムに選択されます。
