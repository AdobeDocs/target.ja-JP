---
keywords: 動的データ、アセット、データ、オファー、パーソナライズオファー、パーソナルオファー、トークン置換
description: 動的データを  [!DNL Adobe Target]  オファーに渡す方法を説明します。
title: 動的データをオファーに渡すにはどうすればよいですか？
feature: Experiences and Offers
exl-id: b8f9c6eb-1000-41a2-aa3f-bc42c1ef5669
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 63%

---

# 動的データをオファーに渡す

[!DNL Adobe Target] プロファイルに保存されている訪問者情報を動的に表示できます。 同様に、アクティビティの名前（アクティビティ名やエクスペリエンス名など）を使用し、訪問者の関心、過去の行動、プロファイル全体に基づいてパーソナライズされたコンテンツを動的に返す単一オファーを作成することもできます。

## ビジネスケース

* 割引オファーを昇格して、最後に購入した製品を「再入力」または「補充」することができます。カタログ内のアイテムごとに個別のオファーを作成する代わりに、動的テキストを使用してオファーを作成し、プロファイルから「最後に購入した製品」を読み取り、オファーにリンクを表示できます。
* 訪問者が、`keyword=world``cup` を含むランディングページに到達します。この場合、「*ワールドカップ*」という用語をオファーに表示します。
* （1）訪問者の買い物かごに最後に追加された商品（Nike Air Max1000s）、（2）訪問者のカラー設定（黒）、（3）訪問者の靴以外のお気に入りのカテゴリ（パーカー）などの情報を含むレコメンデーションラベルをパーソナライズします。例:「クールな『黒』『パーカー』で、あなたの『Nike Air Max 1000』をコーディネートしましょう！」

## 技術的なメリット

訪問者固有の環境設定、行動、ステータスを訪問者のプロファイルに保存できるので、次回の訪問時にこのメッセージを繰り返すことができます。 動的オファーを使用すると、すべての訪問者に対してパーソナライズされたメッセージを表示するアクティビティ内で単一のオファーを設定できるようになるので、より大きな規模で実現できます。訪問者の意図が変わると、あなたの Web サイトのコンテンツは自動的にそれらの変更を反映します。

## 例

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML オファーコード：`Get your ${profile.keyword} information here!`
* World Cup の情報はこちらから！

次の値はトークンで置き換えることができます。

| 値 | 例 |
|--- |--- |
| in-mbox プロファイルパラメーター | `${profile.age}` |
| script プロファイルパラメーター | `${user.lifetimeSpend}` |
| mbox パラメーター | `${mbox.favoriteColor}` |
| キャンペーン情報 | `${campaign.name}`、`${campaign.recipe.name}`、`${campaign.id}`、`${campaign.recipe.id}`、および `${campaign.recipe.trafficType}` |
| 一意の訪問者 ID | `${user.pcId}` |
| 一意のセッション ID | `${user.sessionId}` |
| 訪問者の最初のセッション（true または false） | `${user.isFirstSession}` |
| 過去の行動 | `${user.endpoint.lastPurchasedEntity}`, `${user.endpoint.lastViewedEntity}`, `${user.endpoint.mostViewedEntity}`, `${user.endpoint.categoryAffinity}` |

デバッグ目的でコンソールに `${campaign.name}`、`${campaign.id}`、`${campaign.recipe.name}`、`${campaign.recipe.id}`、`${offer.name}`、`${offer.id}`、`${campaign.name}` などの情報を記録します。

[!DNL Recommendations] のデザインについては、その他の例を [ デザインの概要 ](/help/main/c-recommendations/c-design-overview/design-overview.md) で参照してください。

## 実装

mbox に渡されるプロファイルパラメーターには、次の構文を使用します。

`${profile.parameter}`

プロファイルスクリプトで作成されたプロファイルパラメーターには、次の構文を使用します。

`${user.parameter}`

[!DNL Recommendations] デザインで動的属性を使用する場合、動的値が正しくレンダリングされるようにするには、ドル記号（$）の前にバックスラッシュ（\）を挿入する必要があります。

`\${user.endpoint.lastViewedEntity}`

これらの変数はサーバー側の値で置き換えられるので、引用符やその他の JavaScript がなくても正しく表示されます。

オファーに表示する値にデフォルト値を指定することもできます。 構文は次のようになります。

`${user.testAttribute default="All Items!"}`

`testAttribute` が存在しないか空白の場合は、「All Items!」書き出されています。 空白の属性値が有効で、デフォルト値を表示する代わりに空白の属性値を書き出す必要がある場合は、次の構文を使用できます。

`${user.testAttribute default="All Items!" show_blank="true"}`

表示する値をエスケープしたり、エスケープ解除したりすることもできます。例えば、値にアポストロフィが含まれている場合、ページ上のJavaScriptを壊さないように、値をエスケープできます。 （オファーは JavaScript で書き出されるので、シングルアポストロフィが引用符と見なされて問題になる可能性があります）。次に例を示します。

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`

オファーのコンテンツで使用されるオファーパラメーター（offer.name、offer.id）の場合：

そのオファーがエクスペリエンスに設定された複数のオファーの 1 つである場合、最後に追加されたオファーの値がパラメーターの値に入力されます。 つまり、これらのパラメーターはエクスペリエンスレベルで評価されます。