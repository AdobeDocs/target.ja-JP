---
keywords: recommendations;よくある質問;faq
description: '[!DNL Target Recommendations]のデザインに関するよくある質問（FAQ）とその回答。'
title: デザイン FAQ
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
TQID: 'https://experienceleague.adobe.com/xRu0XEnc8wX8PZngba7CO67mFdja7HALL-1OSnhAmuY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 23%
---
# デザイン FAQ {#design-faq}

>[!BEGINSHADEBOX]

**このページ：** [!DNL Adobe Target] [!DNL Recommendations]のデザインに関するよくある質問への回答を表示します。

>[!ENDSHADEBOX]

+++ 推奨項目の価格は、小数点の右に両方の数字を表示するにはどうすればよいですか？

デフォルトでは、デザインで返される数値（`entity.value`など）は、小数点の後に末尾のゼロを表示しません。 例えば、項目の価格が35.00 ドルの場合、`entity.value`は35に等しく、ページには35のみが表示され、35.00 ドルは表示されません。

この問題に対処するには、次の 2 つの選択肢があります。

* Velocity スクリプトまたはJavaScriptでは、返された値にフォーマットを適用できます。

* 商品の価格は、2つの別々のエンティティ属性に渡すことができます。 最初の `entity.value` は、数値の比較（価格比較ルールなど）に使用します。 2つ目は、適切なレンダリングを可能にするために、エンティティの値を文字列として保存する`entity.displayValue`などのカスタム属性です。

  例：

  `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

+++

+++ $entity1.categoryIdが使用されている場合、カテゴリがデザインに表示されないのはなぜですか？

カテゴリ IDはデザインに表示できません。 複数のカテゴリを保存できるため、どのカテゴリを表示すればよいかわかりません。

+++

+++ デザインを変更して即座に更新するにはどうすればよいですか？

現在使用しているデザインを変更すると、更新までしばらく時間がかかります。 デザインをすぐに変更するには、新しいデザインを作成し、アクティビティでそれを選択して、レコメンデーションを保存します。

+++

+++ キー製品のカテゴリなどのキー情報をデザインに表示するにはどうすればよいですか？

`$key` パラメーターは、デザイン内で表示する主要製品の情報のほとんどをキャプチャします。 例えば、キー製品のサムネールを表示するには、`$key.thumbnailURL`を使用します。

+++

+++ Velocity のどのバージョンが使用されますか？

バージョン 1.7。追加のツールやライブラリは追加されません。 Velocity の基本的な機能を使用できます。

+++

+++ 既存のエンティティ値を空白に置き換える方法（例えば、プロモーションの終了時にアイテムのentity.messageをクリアする必要がある場合など）

JavaScriptの非分割スペースを送信すると、このようになります。 開発者は`\u00A0`を値（例：`entity.message=\u00A0`）として送信します。 値が存在しない場合は、nullではなく、その値をデフォルトとして使用することも考慮できます。

+++

+++ プロファイルスクリプトは[!DNL Recommendations] デザインで使用できますか？

はい。 [!DNL Recommendations] デザインでプロファイルスクリプトを使用するには、名前を `\${...}` で囲みます。 例えば、プロファイルスクリプトの名前が`user.basket`の場合、デザインでは`\${user.basket}`と呼びます。 バックスラッシュは、プロファイルスクリプトがVelocityによってレンダリングされないことを意味します。そのため、Velocity テンプレート内のプロファイルスクリプトに対して操作を実行することはできません。 値がページに直接印刷されます。

+++
