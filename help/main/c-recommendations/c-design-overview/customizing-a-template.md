---
keywords: カスタムデザイン;velocity;小数点;コンマ;デザインのカスタマイズ
description: オープンソースの Velocity デザイン言語を使用して、Adobe  [!DNL Target]  Recommendations のレコメンデーションデザインをカスタマイズする方法を説明します。
title: Velocity を使用してデザインをカスタマイズする方法
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 035d7988-80d8-4080-bb0d-1d0e9f8856d1
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1066'
ht-degree: 76%

---

# Velocity を使用したデザインのカスタマイズ

オープンソースの Velocity デザイン言語を使用して、[!DNL Adobe Target Recommendations] のレコメンデーションデザインをカスタマイズします。

## Velocity の概要 {#section_C431ACA940BC4210954C7AEFF6D03EA5}

Velocity について詳しくは、[https://velocity.apache.org](https://velocity.apache.org) を参照してください。

レコメンデーションのデザインには、Velocity の論理、構文、その他すべてを使用できます。つまりこれは、*for* ループ、*if* ステートメント、およびその他のコードを JavaScript ではなく Velocity を使用して作成できることを意味します。

に送信されたエンティティ属性 [!DNL Recommendations] 内 `productPage` 「複数値」属性を除き、mbox または CSV アップロードをデザインに表示できます。 任意のタイプの属性を送信できます。しかしながら [!DNL Target] は、テンプレートが繰り返し可能な配列として「複数値」型の属性を渡しません ( 例： `entityN.categoriesList`) をクリックします。

これらの値は次の構文で参照されます。

```
$entityN.variable
```

エンティティの属性名は、先頭の *$* 文字に続いて、Velocity Template Language(VTL) 識別子が表示されます。 VTL 識別子は、アルファベット文字（a-z または A-Z）で始まる必要があります。

Velocity エンティティの属性名は、次の文字タイプに制限されます。

* アルファベット（a-z、A-Z）
* 数字（0-9）
* ハイフン（-）
* アンダースコア（_）

次の属性は Velocity 配列として使用できます。 繰り返し処理したり、インデックスで参照したりできます。

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

Velocity 変数（属性）について詳しくは、 [https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables](https://velocity.apache.org/engine/releases/velocity-1.7/user-guide.html#variables).

デザインでプロファイルスクリプトを使用する場合は、スクリプト名の前にある$を `\` （バックスラッシュ）。 次に例を示します。

`\${user.script_name}`

>[!NOTE]
>
>デザインで参照できるエンティティの最大数は、ハードコーディングの場合もループの場合も 99 です。テンプレートスクリプトには、最大 65,000 文字を含めることができます。

例えば、デザインに次のような内容を表示するとします。

![velocity_example 画像](assets/velocity_example.png)

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
>属性名が終了したことを示すタグの前で、属性の値の後にテキストを追加する場合は、正式な表記を使用して属性名を囲むことができます。 例えば、`${entity1.thumbnailUrl}.gif` のようになります。

また、 `algorithm.name` および `algorithm.dayCount` をデザインのエンティティ属性として使用すると、1 つのデザインを使用して複数の条件をテストでき、条件名をデザインに動的に表示できます。 これによって、訪問者に「トップセラー」や「この商品を見た人はこんな商品を買っています」といった内容を表示することができます。これらの属性を使用して、 `dayCount` (「過去 2 日間のトップセラー」などのように、データが条件で使用された日数。

## Velocity テンプレートでの数値の操作

デフォルトでは、Velocity テンプレートは、すべてのエンティティ属性を文字列値として扱います。 数学演算を実行したり、別の数値と比較したりするために、エンティティ属性を数値として扱うことができます。 エンティティ属性を数値として扱うには、次の手順に従います。

1. ダミー変数を宣言し、任意の整数値または double 値に初期化します。
1. 使用するエンティティ属性が空白でないことを確認します ( [!DNL Target Recommendations]「 」テンプレートパーサーを使用して検証および保存します )。
1. 手順 1 で作成したダミー変数の `parseInt` または `parseDouble` メソッドにエンティティ属性を渡し、文字列を整数値または倍精度値に変換します。
1. 新しい数値に対して数学演算または比較を実行します。

### 例：割引価格の計算

値引きを適用するために、品目の表示価格を 0.99 ドル減らすとします。これを実行するには、以下のアプローチを使用します。

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

分単位で保存したムービーの長さを時間と分の単位で表示するとします。これを実行するには、以下のアプローチを使用します。

```
#if( $entity1.get('length_minutes') )
#set( $Integer = 1 )
#set( $nbr = $Integer.parseInt($entity1.get('length_minutes')) )
#set( $hrs = $nbr / 60)
#set( $mins = $nbr % 60)
#end
```

## 重要品目と推奨商品の表示 {#section_7F8D8C0CCCB0403FB9904B32D9E5EDDE}

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

![rec_key 画像](assets/rec_key.png)

[!DNL Recommendations] アクティビティを作成していて、重要品目が「最後に購入された品目」など訪問者のプロファイルから取得されている場合、[!DNL Target] は、[!UICONTROL Visual Experience Composer]（VEC）に商品をランダムに表示します。これは、アクティビティをデザインしている間は、プロファイルを利用できないためです。訪問者がページを表示すると、期待された重要品目が表示されます。

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

エンティティ表示の動的サイズ変更を制御する Velocity スクリプトを使用し、以下のテンプレートを 1 対多の結果に対応させて、[!DNL Recommendations] から返されたエンティティが十分でない場合に空の HTML 要素が作成されるのを回避します。このスクリプトは、バックアップレコメンデーションが意味をなさず、[!UICONTROL テンプレートの部分レンダリングが有効]の場合のシナリオに最適です。

以下の HTML スニペットは、4x2 デフォルトデザインの既存の HTML 部分を置き換えます（ここでは、簡潔にするために CSS は含まれません）。

* 5 番目のエンティティが存在する場合、スクリプトは div 終了タグを挿入し、`<div class="at-table-row">` で新しい行を開始します。
* 4x2 の場合、表示される最大の結果は 8 ですが、これは `$count <=8` を変更することで、より小さい、または大きいリスト用にカスタマイズできます。
* このロジックは、複数の行にあるエンティティのバランスを取らないことに注意してください。例えば、表示するエンティティが 5 個または 6 個ある場合、動的に上に 3 個、下に 2 個（または上に 3 個、下に 3 個）にはなりません。上の行に 4 項目表示してから 2 番目の行が開始します。

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
