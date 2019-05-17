---
description: HTMLまたはJSONオファーに、プロファイル値とアクティビティ情報を直接表示できます。
keywords: 動的データ;assets;data;オファー、パーソナライズオファー、個人オファー;トークン置換
seo-description: HTMLまたはJSONオファーに、プロファイル値とアクティビティ情報を直接表示できます。
seo-title: 動的データをオファーに渡す
solution: 'Target '
title: 動的データをオファーに渡す
topic: Premium
uuid: 1910a7f5-e4bd-413a-9875-e0b005407f50
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# 動的データをオファーに渡す{#pass-dynamic-data-into-offers}

Targetプロファイルに保存されている訪問者情報を動的に表示できます。同様に、アクティビティの名前（アクティビティ名やエクスペリエンス名など）を使用して、訪問者の関心、過去の行動、プロファイル全体に基づいてパーソナライズされたコンテンツを動的に返す単一オファーを作成することもできます。

**ビジネス事例**

* 割引オファーをプロモーションして、購入した最後の製品を「再入力」または「補充」することができます。カタログ内のアイテムごとに個別のオファーを作成する代わりに、動的テキストを使用してオファーを作成し、プロファイルから「最後に購入した製品」を読み取り、オファーにリンクを表示できます。
* 訪問者が、`keyword=world``cup` を含むランディングページに到達します。この場合、「*ワールドカップ*」という用語をオファーに表示します。
* （1）訪問者の買い物かごに追加された最後の品目（Nike Air Max1000s）、（2）訪問者のカラー設定（黒）および訪問者のお気に入りの非靴カテゴリ（hoties）など、情報を含むレコメンデーションラベルをパーソナライズします。例:&quot;Accessorize your&#39;Nike Air Max1000s&#39;with these cool&#39;black&#39;&#39;hoties&#39;!&quot;


**技術上のメリット**

ユーザー固有の環境設定、行動、ステータスなど。ユーザーのプロファイルに保存することができ、次の訪問時にこのメッセージを繰り返すことができます。動的なオファーを使用すると、すべての訪問者向けにパーソナライズされたメッセージを表示するアクティビティ内で単一のオファーを設定することで、より大きなスケールを有効にできます。訪問者の意図が変更されると、Webサイトのコンテンツにはその変更が自動的に反映されます。

**例**

* `mboxCreate("landingpage"`, `"profile.keyword=World Cup");`

* HTML オファーコード：`Get your ${profile.keyword} information here!`
* ユーザーには、「Get your World Cup information here!」が表示されます。

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
| 過去の行動 | `{$user.endpoint.lastPurchasedEntity}`, `{$user.endpoint.lastViewedEntity}`, `{$user.endpoint.mostViewedEntity}`, `{$user.endpoint.categoryAffinity}` |

コンソールにデバッグ用のログ情報（ `${campaign.name}``${campaign.id}``${campaign.recipe.name}``${campaign.recipe.id}``${offer.name}``${offer.id}`、 `${campaign.name}`

Recommendationsデザインについては、「デザイン概要」の [追加の例](/help/c-recommendations/c-design-overview/design-overview.md)を参照してください。

**実装**

プロファイルパラメーターがmboxに渡される場合は、次の構文を使用します。 `${profile.parameter}` プロファイルスクリプトで作成されたプロファイルパラメーターの場合は、次の構文を使用します。

`${user.parameter}`

Recommendationsデザインで動的属性を使用する場合、動的値が正しくレンダリングされるためにはドル記号（&#39;$&#39;）の前にバックスラッシュ（&quot;$&quot;）を挿入する必要があります。 `\${user.endpoint.lastViewedEntity}`

これらの変数はサーバーサイドの値で置き換えられるので、引用符やその他の JavaScript がなくても正しく表示されます。

オファーに表示する値に対して、デフォルト値を指定することもできます。構文は次のようになります。

`${user.testAttribute default="All Items!"}`

`testAttribute` が存在しないか空白の場合は、「All Items!」が書き出されます。空白の属性値が有効で、デフォルト値を表示する代わりに空白の属性値を書き出す必要がある場合は、次の構文を使用できます。

`${user.testAttribute default="All Items!" show_blank="true"}`

表示する値をエスケープしたり、エスケープ解除したりすることもできます。例えば、値にアポストロフィが含まれている場合、ページ上の JavaScript の実行が中止されないように、その値をエスケープできます（オファーは JavaScript で書き出されるので、シングルアポストロフィが引用符と見なされて問題になる可能性があります）。次に例を示します。

`${user.encodedValue encode="unescape"}`

`${user.unencodedValue encode="escape"}`