---
description: Recommendations デザインに関するよくある質問（FAQ）のリストです。
keywords: recommendations;よくある質問;faq
seo-description: Recommendations デザインに関するよくある質問（FAQ）のリストです。
seo-title: デザイン FAQ
solution: 'Target '
title: デザイン FAQ
title-outputclass: premium
topic: Premium
uuid: ac222ade-ddd9-4b32-a16f-4d83b8766384
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) デザイン FAQ{#design-faq}

Recommendations デザインに関するよくある質問（FAQ）のリストです。

## カテゴリがデザインに表示されないのはなぜですか？$entity1.categoryId を使用しています。{#section_073309B8051049C7953D396A93EA0713}

カテゴリ ID は、デザインには表示できません。複数のカテゴリを保存できるので、システムはどのカテゴリを表示すればよいかわかりません。

## すぐに更新されるようにするには、どのようにデザインを変更する必要がありますか？ {#section_28EE35A5B10B47ECA4A332F0E5B2598F}

現在使用しているデザインを変更すると、更新までしばらく時間がかかります。デザインをすぐに変更するには、新しいデザインを作成し、キャンペーンでそれを選択して、レコメンデーションを保存します。

## デザインに表示する主要な情報をどのようにして取り込むことができますか？例えば、主要商品のカテゴリを表示したい場合、Velocity デザインのコードにどのような値を設定したらよいですか？ {#section_F08043B14BA24BC8815FEF25F4F84C39}

`$key. *`値`*`パラメーターは、デザイン内で表示するほとんどの主要商品の情報を取り込みます。例えば、主要商品のサムネールを表示したい場合、`$key.thumbnailURL` を使用します。

## Velocity のどのバージョンが使用されますか？{#section_28F00E15A4A54A768782A3F5BB0CDB21}

バージョン 1.7 で、追加のツールやライブラリアドインは使用していません。Velocity の基本的な機能を使用できます。

## 既存のエンティティの値を空白で置き換えるにはどのようにすればよいですか（プロモーションが終了して、品目の entity.message をクリアする必要がある場合など）？{#section_B88F2C2925DC4508974B2F8B13F961CB}

JavaScript で改行をしないスペースを送信することで可能だと思われます。開発者に `\u00A0` を値として送信してもらいます。（例：`entity.message=\u00A0`）。値が存在しない場合に null の代わりにその値をデフォルトにすることも検討してください。

## Recommendations デザインにプロファイルスクリプトを使用できますか？{#section_6BD55203984A4D80A0C6F241AD7806DF}

はい。ただし、プロファイルスクリプト名にある $ の前にバックスラッシュ（\）を追加する必要があります。
