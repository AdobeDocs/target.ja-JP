---
keywords: カスタムデザイン;velocity;小数点;コンマ;デザインのカスタマイズ
description: オープンソースの [!DNL Velocity]  デザイン言語を使用して、 [!DNL Target] Recommendationsでレコメンデーションデザインをカスタマイズする方法について説明します。
title: Velocity を使用してデザインをカスタマイズする方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
TQID: https://experienceleague.adobe.com/cccBRfwqqn-eL2hraSDAoJHPYSCkcA9tVne3OWDXxEU
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1089
ht-degree: 62%

---

# [!DNL Velocity]を使用したデザインのカスタマイズ

オープンソースの[!DNL Velocity] デザイン言語を使用して、[!DNL Adobe Target Recommendations]でレコメンデーションデザインをカスタマイズします。

## [!DNL Velocity] の概要 {#section_C431ACA940BC4210954C7AEFF6D03EA5}

[!DNL Velocity]に関する情報は、[https://velocity.apache.org](https://velocity.apache.org)にあります。

すべての[!DNL Velocity] ロジックや構文などをレコメンデーションデザインに使用できます。 つまり、*for* ループ、*if* ステートメント、およびJavaScriptではなく[!DNL Velocity]を使用した他のコードを作成できます。

`productPage` mboxまたはCSV アップロードで[!DNL Recommendations]に送信されたエンティティ属性は、「複数値」属性を除いて、デザインに表示できます。 任意のタイプの属性を送信できますが、[!DNL Target]は、テンプレートが反復できる配列として「複数値」タイプの属性を渡しません（例：`entityN.categoriesList`）。

これらの値は次の構文で参照されます。

```
$entityN.variable
```

エンティティ属性名は、[!DNL Velocity]の短縮表記に従う必要があります。この表記は、*$*&#x200B;文字の先頭に[!DNL Velocity] テンプレート言語（VTL）識別子が続きます。 VTL 識別子は、アルファベット文字（a-z または A-Z）で始まる必要があります。

Velocity エンティティ属性名は、次のタイプの文字に制限されています。

* アルファベット（a-z、A-Z）
* 数字（0-9）
* ハイフン（-）
* アンダースコア（_）

次の属性は[!DNL Velocity]配列として使用できます。 繰り返し処理したり、インデックスで参照したりできます。

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

[!DNL Velocity]個の変数（属性）について詳しくは、[https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables)を参照してください。

デザインでプロファイルスクリプトを使用する場合、スクリプト名の前の$は`\` （バックスラッシュ）でエスケープする必要があります。 次に例を示します。

`\${user.script_name}`

>[!NOTE]
>
>デザインで参照できるエンティティの最大数は、ハードコーディングの場合もループの場合も 99 です。 テンプレートスクリプトには、最大 65,000 文字を含めることができます。

例えば、デザインに次のような内容を表示するとします。

![velocity_example image](assets/velocity_example.png)

この場合は以下のようなコードを使用します。

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

>[!NOTE]
>
>属性名が終了したことを示すタグの前に、属性の値の後にテキストを追加する場合は、形式表記法を使用して属性の名前を囲むことができます。 例えば、`${entity1.thumbnailUrl}.gif` のようになります。

デザインで`algorithm.name`と`algorithm.dayCount`をエンティティ属性として使用することもできるので、1つのデザインを使用して複数の条件をテストし、条件名をデザインに動的に表示できます。 これによって、訪問者に「トップセラー」や「この商品を見た人はこんな商品を買っています」といった内容を表示することができます。 これらの属性を使用して、`dayCount` （過去2日間の上位セラーなど、条件で使用されたデータの日数）を表示することもできます。

## [!DNL Velocity] テンプレートでの数値の操作

デフォルトでは、[!DNL Velocity] テンプレートはすべてのエンティティ属性を文字列値として扱います。 数学演算を実行したり、別の数値と比較したりするために、エンティティ属性を数値として扱うことができます。 エンティティ属性を数値として扱うには、次の手順に従います。

1. ダミー変数を宣言し、任意の整数値または double 値に初期化します。
1. 使用するエンティティ属性が空白でないことを確認します（[!DNL Target Recommendations]&#39; テンプレート パーサーがテンプレートを検証および保存するために必要）。
1. 手順 1 で作成したダミー変数の `parseInt` または `parseDouble` メソッドにエンティティ属性を渡し、文字列を整数値または倍精度値に変換します。
1. 新しい数値に対して数学演算または比較を実行します。

### 例：割引価格の計算

値引きを適用するために、品目の表示価格を 0.99 ドル減らすとします。 これを実行するには、以下のアプローチを使用します。

```
#set( $double = 0.1 )

#if( $entity1.get('priceBeforeDiscount') != '' )
    #set( $discountedPrice = $double.parseDouble($entity1.get('priceBeforeDiscount')) - 0.99 )
    Item price: $$discountedPrice
#else
    Item price unavailable
#end
```

### 例：項目の評価に応じて表示する星の数の選択

項目の顧客評価の平均値に基づいて適切な数の星を表示するとします。 これを実行するには、以下のアプローチを使用します。

```
#set( $double = 0.1 )

#if( $entity1.get('rating') != '' )
    #set( $rating = $double.parseDouble($entity1.get('rating')) )
    #if( $rating >= 4.5 )
        <img src="5_stars.jpg">
    #elseif( $rating >= 3.5 )
        <img src="4_stars.jpg">
    #elseif( $rating >= 2.5 )
        <img src="3_stars.jpg">
    #elseif( $rating >= 1.5 )
        <img src="2_stars.jpg">
    #else
        <img src="1_star.jpg">
    #end
#else
    <img src="no_rating_default.jpg">
#end
```

### 例：項目の長さ（分）に基づく時間と分単位での時間の計算

分単位で保存したムービーの長さを時間と分の単位で表示するとします。 これを実行するには、以下のアプローチを使用します。

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## 重要品目と推奨商品の表示 {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

他の推奨商品と並べて重要品目を表示するようにデザインを変更することができます。 例えば、レコメンデーションの隣に参考のため現在の品目を表示してみてはどうでしょうか。

これを行う際のレコメンデーションは、`$entity` 属性ではなく、`$key` 属性を使用するデザインに列を作成することです。 例えば、重要列のコードは次のようになります。

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

![rec_key image](assets/rec_key.png)

[!DNL Recommendations] アクティビティを作成する際に、「最後に購入したアイテム」など、訪問者のプロファイルから主要なアイテムが取得された場合、[!DNL Target]は[!UICONTROL Visual Experience Composer] （VEC）にランダムな製品を表示します。 これは、アクティビティをデザインしている間は、プロファイルを利用できないためです。 訪問者がページを表示すると、期待された重要品目が表示されます。

## 文字列値での置換の実行 {#section_01F8C993C79F42978ED00E39956FA8CA}

デザインを変更して、文字列内の値を置き換えることができます。 例えば、米国で使用されている小数点の区切り文字を、ヨーロッパや他の国で使用されているコンマ区切り文字に置き換えます。

次のコードは、条件付き販売価格の例にある 1 行を示しています。

```
<span class="price">$entity1.value.replace(".", ",") &euro;</span><br>
```

以下のコードは、販売価格の条件全体の例です。

```
<div class="price"> 
    #if($entity1.hasSalesprice==true) 
    <span class="old">Statt <s>$entity1.salesprice.replace(".", ",") &euro;</s></span><br> 
    <span style="font-size: 10px; float: left;">jetzt nur</span> $entity1.value.replace(".", ",") &euro;<br> #else 
    <span class="price">$entity1.value.replace(".", ",") &euro;</span><br> #end 
    <span style="font-weight:normal; font-size:10px;"> 
                                        $entity1.vatclassDisplay 
                                        <br/> 
                                        $entity1.delivery 
                                        <br> 
                                    </span>
```

## テンプレートサイズのカスタマイズと空白値の確認 {#default}

[!DNL Velocity] スクリプトを使用してエンティティ表示の動的なサイズを制御すると、次のテンプレートは、一致するエンティティが[!DNL Recommendations]から返されない場合に空のHTML要素を作成しないように、1対多の結果を含みます。 このスクリプトは、バックアップの推奨事項が意味がなく、[!UICONTROL 部分テンプレートレンダリング &#x200B;]が有効になっているシナリオに最適です。

以下の HTML スニペットは、4x2 デフォルトデザインの既存の HTML 部分を置き換えます（ここでは、簡潔にするために CSS は含まれません）。

* 5 番目のエンティティが存在する場合、スクリプトは div 終了タグを挿入し、`<div class="at-table-row">` で新しい行を開始します。
* 4x2 の場合、表示される最大の結果は 8 ですが、これは `$count <=8` を変更することで、より小さい、または大きいリスト用にカスタマイズできます。
* このロジックは、複数の行にあるエンティティのバランスを取らないことに注意してください。 例えば、表示するエンティティが 5 個または 6 個ある場合、動的に上に 3 個、下に 2 個（または上に 3 個、下に 3 個）にはなりません。 上の行に 4 項目表示してから 2 番目の行が開始します。

```
<div class="at-table">
  <div class="at-table-row">
    #set($count=1) 
    #foreach($e in $entities)  
        #if($e.id != "" && $count < $entities.size() && $count <=8) 
            #if($count==5) 
                </div>
                <div class="at-table-row">
            #end
            <div class="at-table-column">
                <a href="$e.pageUrl"><img src="$e.thumbnailUrl" class="at-thumbnail" />
                    <br/>
                    <h3>$e.name</h3>
                    <br/>
                    <p class="at-light">$e.message</p>
                    <br/>
                    <p class="at-light">$$e.value</p>
                </a>
            </div>
            #set($count = $count + 1) 
        #end 
    #end
  </div>
</div>
```
