---
keywords: 複数値のエンティティ属性;カスタムエンティティ属性;有効な JSON;エンティティ属性値, JSON 配列;複数値
description: Adobe [!DNL Target]のレコメンデーションカタログ内の項目に関する追加情報を定義するために、1つまたは複数の値のカスタムエンティティ属性を使用する方法について説明します。
title: カスタムエンティティ属性の使用方法を教えてください。
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
mini-toc-levels: 3
exl-id: d7d0b04a-0f50-4d30-9cbe-c0347a3d3715
TQID: 'https://experienceleague.adobe.com/eFeg78-PswBCwtpzMR7j5c8FJ03MyQVcSdzo6ctZt3Q'
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
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '1347'
ht-degree: 57%
---
# カスタムエンティティの属性 {#custom-entity-attributes}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、[!DNL Adobe Target Recommendations] カタログの項目を説明する単一および複数値のカスタムエンティティ属性を定義、送信、使用する方法について説明します。

>[!ENDSHADEBOX]

[!DNL Adobe Target Recommendations]で単一および複数値のカスタムエンティティ属性を使用して、カタログ内のアイテムに関する追加情報を定義します。 この情報は、アルゴリズムの包含ルール、カタログルール、除外ルールで使用でき、デザインに表示できます。

## 制限 {#limits}

最大 100 個のカスタムエンティティ属性を使用して、カタログの項目に関する追加情報を定義することができます。 例えば、`entity.genre` という名前のカスタム属性を作成して、書籍や映画を定義できます。 また、チケット業者はイベントが開催される施設の属性を作成して、スポーツイベントでの来訪チームやコンサートの前座など第 2 のパフォーマーを追加することができます。

単一値のカスタムエンティティの属性の最大長は、15,000 文字（英語やその他のラテン文字のアルファベットなどの 1 バイトおよび 2 バイトの UTF-8 でエンコードされた言語の場合）、または 10,000 文字（中国語、日本語、韓国語などの 3 バイトの UTF-8 エンコード言語の場合）です。

複数値のカスタムエンティティ属性には、500 個以下の値を含めることができます。 個々の値はそれぞれ 100 文字以内に制限されています。 すべての値の合計文字数は、単一値エンティティのカスタム属性の最大長の制限に準拠する必要があります（上記を参照）。

## カスタムエンティティ属性値 {#section_313331A9F8194A89B5EDD89363018651}

カスタムエンティティ属性には、単一値または複数値を設定できます。 エンティティ属性値は製品表示で表示されます。

![multi-value_product image](assets/multi-value_product.png)

単一値のカスタムエンティティ属性は、単一値の定義済みエンティティ属性と同じように構成されます。

`entity.genre=genre1`

複数値のカスタムエンティティ属性は、有効な JSON 配列として送信する必要があります。

`entity.genre=["genre1", "genre2"]`

[!DNL Recommendations] で使用できる有効な JSON 配列の例を以下に示します。

* `["AB","BC"]` すべての値が文字列
* `[1,2]` すべての値が数値

>[!NOTE]
>
>[!DNL Recommendations] では複数値のエンティティ属性で値の種類を混在させることはできません。 例えば、`["AB",1,true, [1,2,3]]` は有効な JSON 配列ではありますが、値の種類（文字列、数値、ブール値、オブジェクト）が混在しているので、[!DNL Recommendations] では使用できません。

カスタム属性は、有効な JSON 配列として送信されると、カタログ内のすべての製品について複数値の属性として扱われます。

>[!NOTE]
>
>属性を複数値から単一値に変更するには、カタログを削除して、修正後の製品データをアップロードする必要があります。 カタログを削除しても、製品 ID に関連付けられた履歴データは削除されません。 詳細については、『*Adobe Recommendations Classic*』ドキュメントの「[システムからすべての項目を削除](/help/main/assets/adobe-recommendations-classic.pdf)」を参照してください。

**制限事項**：

* 事前定義されたエンティティの属性名はカスタムエンティティの属性に使用できません。 （[エンティティ属性](/help/main/c-recommendations/c-products/entity-attributes.md#entity-attributes)を参照。）
* 属性 `entity.environment` はシステムによって予約されており、カスタムエンティティの属性には使用できません。 `entity.environment`、フィードまたは API を使用して `targetPageParams` を渡そうとしても無視されます。
* 配列には単一値が含まれている必要があります。 値の種類が混在する配列（`["AB",1,true]`）は使用できません。
* 複数値の属性で入れ子になっている JSON 配列（`[10,12,[1,2,3]]`）は単一値の属性として扱われます。

## 複数値の属性の実装 {#section_80FEFE49E8AF415D99B739AA3CBA2A14}

フィード （CSV）、`targetPageParams`、および配信APIを使用して製品をアップロードする場合、複数値のカスタムエンティティ属性がサポートされます。 新しい値によって現在の値は置き換えられます。新しい値が現在の値の後には追加されることはありません。 空の配列（[]）は、値がないとして扱われます。

二重引用符は、エスケープする必要があります。 例えば、`"[""test"", ""value""]"` は CSV で使用できる有効な JSON 配列です。

### targetPageParamsの使用

次の例は、`targetPageParams`の使用方法を示しています。

```javascript
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds':                  '[123, 3232, 2323, 4344]', 
    'orderId':                      '123456', 
    'orderTotal':                   '195.32', 
    'productPurchaseId':            '[001,002,003]' 
  }; 
}
```

### CSVの使用

CSV ファイルの管理は、テキストエディターで生データの形式でおこなうか、スプレッドシートソフトウェアを利用します。

この生データの CSV は次のような形式です。

![multi-value_example_raw image](assets/multi-value_example_raw.png)

このカタログはスプレッドシートでは次のようになります。

![multi-value_example_excel image](assets/multi-value_example_excel.png)

スプレッドシートソフトウェアは、.csv 形式に変換する際に、セルの内容に二重引用符を追加します。これにより、セル内のコンマが列区切り記号として認識されることを防ぎます。 また、複数値のカスタム属性に含めた JSON 文字列値の前後にも二重引用符が追加されます。 このため、生データのファイルを直接編集することはお勧めできません。 次に例を示します。

* スプレッドシート：`["1","2","3"]`
* 生データ：`"[""1"",""2"",""3""]"`

生のカタログ CSV ファイルを直接編集する場合は注意してください。

### APIの使用

mbox パラメーターの配信APIを使用して、エスケープされたJSON配列を含む文字列値として複数値属性を渡すことができます。

```javascript
"execute": {
    "mboxes": [
      {
        "index": 0,
        "name": "first-mbox",
        "parameters": {
          "entity.id": "32323",
          "entity.categoryId": "My Category",
          "entity.MultiValueAttribute": "[\"X\", \"Y\", \"Z\"]"
        }
      }
    ]
  }
```

配信および保存エンティティ APIの使用について詳しくは、[Adobe Recommendations API ドキュメント ](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=ja){target=_blank}を参照してください。

## 複数値の属性を持つ演算子の使用 {#section_83C2288A805242D9A02EBC4F07DEE945}

アルゴリズムインクルージョンルール、カタログルール、エクスクルージョンルールで複数値のカスタム属性に演算子を適用する場合、リストの値のうち少なくとも 1 つが演算を通過する場合（ブール演算子 *OR*）、結果は *true* になります。

次の例では、ルールは`message contains abc`です。

* 例 1：`entity.genre = ["ab", "bc", "de"]`。 結果は false になります。どの値にも `abc` は含まれていません。
* 例 2：`entity.genre = ["abcde","de","ef"]`。 結果は true になります。1 つの値に `abc` が含まれています。

否定演算子の場合、すべての属性値が通過する必要があります（ブール演算子 *AND*）。 例えば、演算子が`notEquals`の場合、値が一致する場合、結果は&#x200B;*false*&#x200B;になります。

次の表に、各演算子の動作を示し、各ルールの例を示します。

| 演算子 | 次の場合、結果はtrueです | ルールの例 | 属性値 | 結果 | 理由 |
|---|---|---|---|---|---|
| 次と等しい | 任意の属性値が入力値に等しい。 | `genre equals abc` | `["ab", "bc", "de"]` | False | `abc`に等しい値はありません。 |
|  |  |  | `["abc", "de", "ef"]` | True | 1つの値は`abc`に等しいです。 |
|  |  |  | `["abcde", "de", "ef"]` | False | `abc`は、リスト内のどの要素にも等しくありません。 |
| 次と等しくない | 属性値が入力値に等しい場合はありません。 | `genre not equals abc` | `["ab", "bc", "de"]` | True | `abc`に等しい値はありません。 |
|  |  |  | `["abc", "de", "ef"]` | False | 1つの値は`abc`に等しいです。 |
|  |  |  | `["abcde", "de", "ef"]` | True | `abc`は、リスト内のどの要素にも等しくありません。 |
| 次を含む | 任意の属性値には、入力値が含まれます。 | `genre contains abc` | `["ab", "bc", "de"]` | False | 値に`abc`が含まれていません。 |
|  |  |  | `["abcde", "de", "ef"]` | True | 1つの値に`abc`が含まれています。 |
| 次を含まない | 属性値に入力値が含まれていません。 | `genre does not contain abc` | `["ab", "bc", "de"]` | True | 値に`abc`が含まれていません。 |
|  |  |  | `["abcde", "de", "ef"]` | False | 1つの値に`abc`が含まれています。 |
| 次の語句で始まる | 任意の属性値は、入力値で始まります。 | `genre starts with abc` | `["ab", "bc", "de"]` | False | `abc`で始まる値はありません。 |
|  |  |  | `["abcde", "de", "ef"]` | True | 1つの値は`abc`で始まります。 |
|  |  |  | `["ab", "de", "abc"]` | True | 1つの値が`abc`で始まります（必ずしもリストの最初の要素ではありません）。 |
| 次の語句で終わる | 任意の属性値は入力値で終わります。 | `genre ends with abc` | `["ab", "bc", "de"]` | False | `abc`で終わる値はありません。 |
|  |  |  | `["deabc", "de", "ef"]` | True | 1つの値は`abc`で終わります。 |
| 次よりも大きいか等しい（数値のみ） | 任意の属性値が入力値以上である。 各値はdoubleに変換され、変換できない値はルールの実行中にスキップされます。 | `price greater than or equal to 100` | `["10", "20", "45", "de"]` | False | 100以上の値はありません。 「`de`」は倍精度に変換できないためスキップされています。 |
|  |  |  | `["100", "101", "90", "80"]` | True | 2つの値が100以上です。 |
| 次よりも小さいか等しい（数値のみ） | 任意の属性値が入力値以下である。 各値はdoubleに変換され、変換できない値はルールの実行中にスキップされます。 | `price less than or equal to 100` | `["101", "200", "141", "de"]` | False | 100以下の値はありません。 「`de`」は倍精度に変換できないためスキップされています。 |
|  |  |  | `["100", "101", "90", "80"]` | True | 2つの値が100以下です。 |
| 動的に一致（項目ベースのアルゴリズムの場合のみ） | 任意の属性値が入力値と一致します。 | `genre matches abc` | `["ab", "bc", "de"]` | False | `abc`に一致する値はありません。 |
|  |  |  | `["abc", "de", "ef"]` | True | 1つの値が`abc`に一致します。 |
| 動的に一致しない（項目ベースのアルゴリズムでのみ使用可能） | 入力値と一致する属性値はありません。 任意の属性値が一致する場合、結果はfalseになります。 | `genre does not match abc` | `["ab", "bc", "de"]` | True | `abc`に一致する値はありません。 |
|  |  |  | `["abc", "de", "ef"]` | False | 1つの値が`abc`に一致します。 |
| 動的な範囲にある（項目ベースのアルゴリズムでのみ使用可能、数値のみ） | 任意の数値属性値は、指定した範囲内にあります。 | `price dynamically ranges in 80% to 120% of 100` | `["101", "200", "125", "de"]` | True | `101`は100の80%から120%の範囲です。 「`de`」は倍精度に変換できないためスキップされています。 |
|  |  |  | `["130", "191", "60", "75"]` | False | 値は80%から100%の範囲にはありません。 |

>[!NOTE]
>
>*倍精度*&#x200B;は Java のデータタイプです。 数値が必要な演算子の場合、倍精度に変換すると、数値以外の値は結果の判定から除外されます。

## デザイン内の複数値の属性 {#section_F672E4F6E1D44B3196B7ADE89334ED4A}

複数値の属性は、デザインで参照する場合はコンマ区切りのリストとして表示されます。

例：

設計で `entity.genre=["genre1","genre2"]` が `$entity<N>.genre` として参照されている場合、結果は「`genre1, genre2`」になります。

## 関連トピック

* [エンティティの属性](/help/main/c-recommendations/c-products/entity-attributes.md#entity-attributes)
