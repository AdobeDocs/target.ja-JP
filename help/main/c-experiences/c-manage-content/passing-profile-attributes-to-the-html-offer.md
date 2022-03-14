---
keywords: 動的データ、アセット、データ、オファー、パーソナライズオファー、パーソナルオファー、トークン置換
description: に動的データを渡す方法を説明します。 [!DNL Adobe Target] オファー。
title: 動的データをオファーに渡す方法を教えてください。
feature: Experiences and Offers
exl-id: b8f9c6eb-1000-41a2-aa3f-bc42c1ef5669
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 63%

---

# 動的データをオファーに渡す

訪問者情報を動的に表示するには、 [!DNL Adobe Target] プロファイル。 同様に、アクティビティの名前（アクティビティ名やエクスペリエンス名など）を使用し、訪問者の関心、過去の行動、プロファイル全体に基づいてパーソナライズされたコンテンツを動的に返す単一オファーを作成することもできます。

## ビジネス事例

* 割引オファーを昇格して、最後に購入した製品を「再入力」または「補充」することができます。カタログ内のアイテムごとに個別のオファーを作成する代わりに、動的テキストを使用してオファーを作成し、プロファイルから「最後に購入した製品」を読み取り、オファーにリンクを表示できます。
* 訪問者が、`keyword=world``cup` を含むランディングページに到達します。この場合、「*ワールドカップ*」という用語をオファーに表示します。
* （1）訪問者の買い物かごに最後に追加された商品（Nike Air Max1000s）、（2）訪問者のカラー設定（黒）、（3）訪問者の靴以外のお気に入りのカテゴリ（パーカー）などの情報を含むレコメンデーションラベルをパーソナライズします。例:「クールな『黒』『パーカー』で、あなたの『Nike Air Max 1000』をコーディネートしましょう！」

## 技術上のメリット

訪問者固有の設定、行動、ステータスは訪問者のプロファイルに保存できるので、次回の訪問時にこのメッセージを繰り返すことができます。 動的オファーを使用すると、すべての訪問者に対してパーソナライズされたメッセージを表示するアクティビティ内で単一のオファーを設定できるようになるので、より大きな規模で実現できます。訪問者の意図が変わると、あなたの Web サイトのコンテンツは自動的にそれらの変更を反映します。

## 例

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML オファーコード：`Get your ${profile.keyword} information here!`
* 訪問者に表示される内容：World Cup の情報をこちらから入手します。

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

の場合 [!DNL Recommendations] デザイン、「その他の例を参照 [デザインの概要](/help/main/c-recommendations/c-design-overview/design-overview.md).

## 実装

プロファイルパラメーターを mbox に渡す場合は、次の構文を使用します。

`${profile.parameter}`

プロファイルスクリプトで作成するプロファイルパラメーターの場合は、次の構文を使用します。

`${user.parameter}`

動的属性を [!DNL Recommendations] デザインでは、動的な値を正しくレンダリングするには、ドル記号 ( $ ) の前にバックスラッシュ ( \ ) を挿入する必要があります。

`\${user.endpoint.lastViewedEntity}`

これらの変数はサーバー側の値で置き換えられるので、引用符やその他の JavaScript がなくても正しく表示されます。

オファーに公開する値に対しては、デフォルト値も指定できます。 構文は次のようになります。

`${user.testAttribute default="All Items!"}`

`testAttribute` が存在しないか空白の場合は、「All Items!」が書き出されます。 空白の属性値が有効で、デフォルト値を表示する代わりに空白の属性値を書き出す必要がある場合は、次の構文を使用できます。

`${user.testAttribute default="All Items!" show_blank="true"}`

表示する値をエスケープしたり、エスケープ解除したりすることもできます。例えば、値にアポストロフィが含まれている場合、ページ上の JavaScript が壊れないように、値をエスケープできます。 （オファーは JavaScript で書き出されるので、シングルアポストロフィが引用符と見なされて問題になる可能性があります）。次に例を示します。

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`

オファーのコンテンツで使用されるオファーパラメーター (offer.name、offer.id) の場合：

そのオファーが 1 つのエクスペリエンスで設定された複数のオファーのいずれかである場合、最後に追加したオファーの値によってパラメーターの値が設定されます。 つまり、これらのパラメーターはエクスペリエンスレベルで評価されます。