---
description: オープンソースの Velocity デザイン言語を使用して、レコメンデーションデザインをカスタマイズします。
keywords: カスタムデザイン;velocity;小数点;コンマ;デザインのカスタマイズ
seo-description: オープンソースの Velocity デザイン言語を使用して、レコメンデーションデザインをカスタマイズします。
seo-title: Velocity を使用したデザインのカスタマイズ
solution: 'Target '
title: Velocity を使用したデザインのカスタマイズ
title-outputclass: premium
topic: Premium
uuid: 80701a15-c5eb-4089-a92e-117eda11faa2
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Velocity を使用したデザインのカスタマイズ{#customize-a-design-using-velocity}

オープンソースの Velocity デザイン言語を使用して、レコメンデーションデザインをカスタマイズします。

## Velocity の概要 {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Velocity について詳しくは、[](https://velocity.apache.org)https://velocity.apache.org を参照してください。

すべての Velocity 論理、構文、その他を、レコメンデーションデザインに使用できます。つまりこれは、*for* ループ、*if* ステートメント、およびその他のコードを JavaScript ではなく Velocity を使用して作成できることを意味します。

`productPage` mbox または CSV アップロード内の [!DNL Recommendations] に送られた変数は、すべてデザインで表示できます。これらの値は次の構文で参照されます。

```
$entityN.variable
```

変数名は、*$* 文字で始まり、Velocity テンプレート言語（VTL）識別子が続く構成の Velocity 短縮形表記法に従う必要があります。VTL 識別子は、アルファベット文字（a-z または A-Z）で始まる必要があります。

Velocity 変数名は、次の文字に制限されます。

* アルファベット（a-z、A-Z）
* 数字（0-9）
* ハイフン（-）
* アンダースコア（_）

次の変数は Velocity 配列として利用できるので、繰り返し処理したり、インデックスで参照したりできます。

* `entities`
* `entityN.categoriesList`

次に例を示します。

```
#foreach ($category in $entity1.categoriesList) 
<br/>$category 
#end
```

または

```
#if ($entities[0].categoriesList.size() >= 3 ) 
$entities[0].categoriesList[2] 
#end
```

Velocity 変数について詳しくは、[https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables) を参照してください。

デザインでプロファイルスクリプトを使用する場合は、スクリプト名の前にある $ は \ でエスケープする必要があります。例： `\${user.script_name}`

>[!NOTE]
>
>デザインで参照できるエンティティの最大数は、ハードコーディングでもループ経由でも 99 です。テンプレートスクリプトには、最大 65,000 文字を含めることができます。

例えば、デザインに次のような内容を表示するとします。

![](assets/velocity_example.png)

以下のコードが使用できます。

```
<table style="border:1px solid #CCCCCC;"> 
 
<tr> 
 
<td colspan="3" style="font-size: 130%; border-bottom:1px solid  
#CCCCCC;"> You May Also Like... </td> 
 
</tr> 
 
<tr> 
 
<td style="border-right:1px solid #CCCCCC;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity1.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity1.id</a></div> 
 
By $entity1.message <a href="?x14=brand;q14=$entity1.message"> 
(More)</a><br/> 
 
sku: $entity1.prodId<br/> Price: $$entity1.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
<td style="border-right:1px solid #CCCCCC; padding-left:10px;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity2.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity2.id</a></div> 
 
By $entity2.message <a href="?x14=brand;q14=$entity2.message"> 
(More)</a><br/> 
 
sku: $entity2.prodId<br/> 
 
Price: $$entity2.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
<td style="padding-left:10px;"> 
 
<div class="search_content_inner" style="border-bottom:0px;"> 
 
<div class="search_title"><a href="$entity3.pageUrl"  
style="color: rgb(112, 161, 0); font-weight: bold;"> 
$entity3.id</a></div> 
 
By $entity3.message <a href="?x14=brand;q14=$entity3.message"> 
(More)</a><br/> 
 
sku: $entity3.prodId<br/> Price: $$entity3.value 
 
<br/><br/> 
 
</div> 
 
</td> 
 
</tr> 
 
</table>
```

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>変数値の後に情報を追加したい場合、正式な表記法を使用しておこなうことができます。例：`${entity1.thumbnailUrl}.gif`

また、デザインで `algorithm.name` と `algorithm.dayCount` を変数として使用できるので、1 つのデザインで複数の条件をテストでき、条件名をデザインに動的に表示できます。これによって、訪問者に「トップセラー」や「この商品を見た人はこんな商品を買っています」といった内容を表示することができます。これらの変数はまた `dayCount`（「過去 2 日間のトップセラー」などのように、データがその条件で使用された日数）の表示にも使用できます。

## シナリオ：重要品目を推奨商品と共に表示する {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

他の推奨商品と並べて重要品目を表示するようにデザインを変更することができます。例えば、レコメンデーションの隣に参考のため現在の品目を表示してみてはどうでしょうか。

これをおこなうには、`$entity` 属性ではなく、`$key` 属性を使用するデザインに列を作成します。例えば、重要列のコードは次のようになります。

```
<div class="at-table-column"> 
   <a href="$key.pageURL"> 
      <img src=$key.thumbnailUrl" class="at-thumbnail"/> 
      <br/><h3>$key.name</h3> 
      <br/><p class="at-light">$key.message</p> 
      <br/><p class="at-light">$key.value</p> 
   </a> 
</div>
```

結果は次のようなデザインになります。1 列が重要品目を表示しています。

![](assets/rec_key.png)

[!DNL Recommendations] アクティビティを作成していて、重要品目が「最後に購入された品目」など訪問者のプロファイルから取得されている場合、[!DNL Target] は、[!UICONTROL Visual Experience Composer]（VEC）に商品をランダムに表示します。これは、アクティビティをデザインしている間は、プロファイルを利用できないためです。訪問者がページを表示すると、期待された重要品目が表示されます。

## シナリオ：販売価格の小数点をコンマ区切りに置き換える {#section_01F8C993C79F42978ED00E39956FA8CA}

米国で使用されている小数点区切りを、ヨーロッパおよびその他の国で使用されているコンマ区切りに置き換えるようにデザインを変更できます。

次のコードは、条件付き販売価格の例にある 1 行を示しています。

```
<span class="price">$entity1.value.replace(".", ",") €</span><br>
```

次のコードは、販売価格の完全な条件の例です。

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") €</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") €<br> #else 
    <span class="price">$entity1.value.replace(".", ",") €</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

