---
keywords: recommendations;よくある質問;faq
description: Adobe  [!DNL Target]  Recommendations デザインに関するよくある質問（FAQ）とその回答のリストを確認します。
title: ' [!DNL Target]  Recommendations デザインに関する質問への回答'
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: e970f734-9bc7-43b8-af1b-75e527d6353c
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '455'
ht-degree: 100%

---

# デザイン FAQ

[!DNL Adobe Target] [!DNL Recommendations] デザインに関するよくある質問（FAQ）のリストです。

## 推奨品目の価格で小数点の右側に値が表示されません。どうすれば表示できますか？

デフォルトでは、デザインテンプレートで返される数値（`entity.value` など）には、小数点の後の末尾のゼロは表示されません。例えば、品目が $35.00 の場合、`entity.value` は 35 に等しくなり、$35.00 ではなく、35 のみがページに表示されます。

この問題に対処するには、次の 2 つの選択肢があります。

* Velocity スクリプトまたは JavaScript を使用して、戻り値に書式を適用します。

* 品目の価格を 2 つの異なるエンティティ属性に渡すことができます。最初の `entity.value` は、数値の比較（価格比較ルールなど）に使用します。2 番目は、適切にレンダリングできるようにエンティティの値を文字列として格納するカスタム属性（`entity.displayValue` など）である必要があります。

   例：

   `"entity.value" : 35.00, "entity.displayValue" : "$35.00"`

## カテゴリがデザインに表示されないのはなぜですか？`$entity1.categoryId` を使用しています。{#section_073309B8051049C7953D396A93EA0713}

カテゴリ ID は、デザインには表示できません。複数のカテゴリを保存できるので、システムはどのカテゴリを表示すればよいかわかりません。

## すぐに更新されるようにするには、どのようにデザインを変更する必要がありますか？ {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

現在使用しているデザインを変更すると、更新までしばらく時間がかかります。デザインをすぐに変更するには、新しいデザインを作成し、アクティビティでそれを選択して、レコメンデーションを保存します。

## デザインに表示する主要な情報をどのようにして取り込むことができますか？例えば、主要商品のカテゴリを表示したい場合、Velocity デザインのコードにどのような値を設定したらよいですか？ {#section_F08043B14BA24BC8815FEF25F4F84C39}

`$key. *`値`*`パラメーターは、デザイン内で表示するほとんどの主要商品の情報を取り込みます。例えば、主要商品のサムネールを表示したい場合、`$key.thumbnailURL` を使用します。

## Velocity のどのバージョンが使用されますか？ {#section_28F00E15A4A54A768782A3F5BB0CDB21}

バージョン 1.7 で、追加のツールやライブラリアドインは使用していません。Velocity の基本的な機能を使用できます。

## 既存のエンティティの値を空白で置き換えるにはどのようにすればよいですか（プロモーションが終了して、品目の entity.message をクリアする必要がある場合など）？ {#section_B88F2C2925DC4508974B2F8B13F961CB}

JavaScript で改行なしスペースを送信することで可能と思われます。開発者に `\u00A0` を値として送信してもらいます。（例：`entity.message=\u00A0`）。値が存在しない場合に null の代わりにその値をデフォルトにすることも検討してください。

## [!DNL Recommendations] デザインでプロファイルスクリプトを使用できますか？ {#section_6BD55203984A4D80A0C6F241AD7806DF}

はい。[!DNL Recommendations] デザインでプロファイルスクリプトを使用するには、名前を `\${...}` で囲みます。例えば、プロファイルスクリプトの名前が `user.basket` の場合は、デザインで `\${user.basket}` として参照します。バックスラッシュは、プロファイルスクリプトが Velocity でレンダリングされないことを意味します。したがって、Velocity テンプレート内のプロファイルスクリプトに対して操作を実行することはできません。値はページに直接出力されます。
