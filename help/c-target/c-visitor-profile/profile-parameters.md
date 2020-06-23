---
keywords: Profile script;profile script attributes;profile script best practices;debug;debugging;scripts;profile scripts;attributes;attribute;parameter
description: プロファイル属性は、訪問者に固有のパラメーターです。プロファイル属性は訪問者のプロファイルに保存され、Adobe Target アクティビティで使用可能な訪問者に関する情報を提供します。
title: Adobe Target のプロファイル属性
topic: Advanced,Standard,Classic
uuid: a76ed523-32cb-46a2-a2a3-aba7f880248b
translation-type: tm+mt
source-git-commit: 4b7f7cbeb83d98568ec65e3260b4f78e8fca8ad9
workflow-type: tm+mt
source-wordcount: '2442'
ht-degree: 79%

---


# プロファイル属性{#profile-attributes}

プロファイル属性は、訪問者に固有のパラメーターです。プロファイル属性は訪問者のプロファイルに保存され、アクティビティで使用可能な訪問者に関する情報を提供します。

ユーザープロファイルには、年齢、性別、購入商品、最終訪問時など、Webページ訪問者の人口統計や行動に関する情報が含まれ、Targetが訪問者に提供するコンテンツをパーソナライズするために使用します。

訪問者がWebサイトを閲覧したり、訪問者が別のセッションに戻ったりする際に、プロファイルに保存されたプロファイル属性を使用して、コンテンツのターゲットや、セグメントフィルタリングの情報のログを作成できます。

プロファイル属性を設定するには：

1. **[!UICONTROL オーディエンス]** / **[!UICONTROL プロファイルスクリプトをクリックします。]**

   ![「プロファイルスクリプト」タブ](/help/c-target/c-visitor-profile/assets/profile-scripts.png)

1. 「スクリプト **[!UICONTROL を作成]**」をクリックします。

   ![プロファイルスクリプトを作成ダイアログボックス](/help/c-target/c-visitor-profile/assets/create-script.png)

   以下のタイプのプロファイル属性を利用できます。

   | パラメータータイプ | 説明 |
   |--- |--- |
   | mbox | mbox を作成するときに、ページコードを介して直接渡されます。詳しくは、[グローバルmboxへのパラメーターの引き渡し](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) を参照してください。<br>**注意&#x200B;**：Target には、mbox 呼び出しごとに 50 個の独自のプロファイル属性という制限があります。50 個を超えるプロファイル属性を Target に渡す必要がある場合、プロファイル更新 API メソッドを使用して渡すことができます。For more information, see[Profile Update  in the Adobe Target API documentation](http://developers.adobetarget.com/api/#updating-profiles). |
   | プロファイル | JavaScript コードスニペットにより直接定義されます。これらのパラメーターは、現在の合計数（顧客が支払った合計金額など）を保存することができ、mbox リクエストごとに実行されます。詳しくは、プロファイルスクリプト属性を参照してください。 |

## プロファイルスクリプト属性 {#concept_8C07AEAB0A144FECA8B4FEB091AED4D2}

関連する JavaScript コードスニペットを使用して、プロファイルスクリプト属性を定義します。

プロファイルスクリプトを使用して、複数の訪問にわたり、訪問者の属性を取得できます。プロファイルスクリプトは、サーバー側の JavaScript の形式を使用して、Target 内で定義するコードスニペットです。例えば、プロファイルスクリプトを使用して、訪問者がサイトを訪問する頻度や前回の訪問日時を取得できます。

プロファイルスクリプトは、プロファイルパラメーターとは異なります。プロファイルパラメーターでは、Target の mbox コード実装を使用して、訪問者に関する情報を取得します。

## プロファイルスクリプトの作成 {#section_CB02F8B97CAF407DA84F7591A7504810}

プロファイルスクリプトは、[!UICONTROL  インターフェイスの「]オーディエンス[!DNL Target]」タブで使用できます。

新しいプロファイルスクリプトを追加するには、 **[!UICONTROL 「プロファイルスクリプト]** 」タブをクリックし **[!UICONTROL 、スクリプト]** を作成してスクリプトを作成します。

または

To copy an existing profile script, from the [!UICONTROL Profile Scripts] list, hover over the desired script, then click the **[!UICONTROL Copy]** icon: ![copy icon](/help/c-target/c-visitor-profile/assets/icon_copy.png)

これにより、そのオーディエンスを編集して類似のオーディエンスを作成することができます。

![プロファイルスクリプトを作成ダイアログボックス](assets/profile-script.png)

プロファイルスクリプトは、各場所リクエストでプロファイル属性「catchers」を実行します。場所リクエストを受信すると、Target はどのアクティビティを実行するかを決定し、そのアクティビティおよびそのエクスペリエンスに適したコンテンツを表示し、アクティビティの成功を追跡し、関連するプロファイルスクリプトを実行します。これにより、訪問者の場所、時間帯、訪問者がサイトを訪問した回数、購入歴があるかなど、訪問に関する情報を追跡できます。 この情報は次に、訪問者のプロファイルに追加され、サイトでの訪問者のアクティビティをより詳細に追跡できます。

プロファイルスクリプト属性では、属性名の前に `user.` タグが挿入されます。次に例を示します。

```
if (mbox.name == 'Track_Interest') { 
    if (profile.get('model') == "A5" &&; profile.get('subcat') == "KS6") { 
        return (user.get('A5KS6') || 0) + 1; 
    } 
}
```

次の情報に注意してください。

* コード内で、`user.get('parameterName')` を使用して、プロファイルスクリプト属性をいくつか参照します（定義中のパラメーター自体も含む）。
* `user.setLocal('variable_name', 'value')` を使用すると、スクリプトを次回実行するとき（次の mbox リクエストの発生時）にアクセスされる可能性がある変数を保存できます。変数を参照 `user.getLocal('variable_name')` します。これは、最後のリクエストの日時を参照する場合に便利です。
* パラメーターおよび値の大文字と小文字は区別されます。オーディエンスまたはテストの実行中に受け取るパラメーターおよび値の大文字と小文字を一致させてください。
* その他の JavaScript 構文については、後述の「スクリプトプロファイルパラメーターに関する JavaScript リファレンス」を参照してください。
* スクリプトを無効にした後も、プロファイルーには引き続きパラメーターが表示されます。 プロファイルに既にアクティビティのオーディエンスーで使用されているパラメーターが含まれている場合、そのアクティビティに該当します。
* プロファイルスクリプトは、アクティビティで使用中は削除できません。
* あるプロファイルスクリプトの結果を別のプロファイルスクリプトで使用する依存プロファイルスクリプトを作成することはお勧めしません。 プロファイルスクリプトの実行順序は保証されません。

## プロファイルスクリプト情報カードの表示 {#section_18EA3B919A8E49BBB09AA9215E1E3F17}

オファー情報カードに似たプロファイルスクリプト情報ポップアップカードを表示できます。これらのプロファイルスクリプト情報カードでは、選択したプロファイルスクリプトを参照しているアクティビティのリストやその他の有用なメタデータが表示されます。

例えば、次のプロファイルスクリプト情報カードは、プロファイルスクリプトリスト（Audiences／プロファイルスクリプト）のプロファイルスクリプトにマウスポインターを置いてから、情報アイコンをクリックしてアクセスします。

「[!UICONTROL スクリプト情報]」タブには、「名前」、「ステータス」、「トークンの種類」、「スクリプト ID」、「変更ログ」、「説明」の各情報が含まれています。

![プロファイルスクリプト情報カード](assets/profile_script_info_card.png)

「[!UICONTROL スクリプト使用状況]」タブには、選択したプロファイルスクリプトを参照するアクティビティ（およびワークスペース）が一覧表示されます。

![プロファイルスクリプト情報カード／「スクリプトの使用状況」タブ](assets/profile_script_info_card_usage_tab.png)

>[!Note]
>
>次の状況では、選択したプロファイルスクリプトを参照するアクティビティは「スクリプトの使用」タブに表示されません。
> * アクティビティのステータスがドラフトの場合。
> * アクティビティで使用されるコンテンツまたはオファーが、スクリプト変数（アクティビティ内のインラインオファーまたはオファーライブラリ内のオファー）を使用する場合。


## 特定の状況での Target によるプロファイルスクリプトの無効化 {#section_C0FCB702E60D4576AD1174D39FBBE1A7}

[!DNL Target] 実行に時間がかかりすぎたり、命令が多すぎるなど、特定の状況でプロファイルスクリプトを自動的に無効にします。

プロファイルスクリプトが無効化されると、次に示すように、Target UI のプロファイルスクリプトの横に黄色の警告アイコンが表示されます。

![](assets/profile_script_invalid.png)

マウスポインターを重ねると、次のように、エラーの詳細が表示されます。

![](assets/profile_script_hover.png)

システムがプロファイルスクリプトを無効にする一般的な理由は次のとおりです。

* 未定義の変数が参照されている。
* 無効な値が参照されている。これは、多くの場合、URL 値およびその他のユーザー入力データを適切な検証なしに参照することが原因です。
* 使用される JavaScript 命令が多すぎる。Target には、スクリプトあたり 2,000 の JavaScript 命令という制限がありますが、これは、手作業で JavaScript を読んで単純に計算することはできません。例えば、Rhino は、すべての関数呼び出しと「新規」呼び出しを 100 個の命令として処理します。つまり、任意の関数を呼び出すと、100個の命令が消費されます。 また、すべてのエントリデータのサイズ（URL 値など）は、命令数に影響を与える可能性があります。
* 後述の[ベストプラクティス](../../c-target/c-visitor-profile/profile-parameters.md#section_64AFE5D2B0C8408A912FC2A832B3AAE0)の節で取り上げられている項目に従っていない。

## ベストプラクティス{#best}

次のガイドラインは、エラーや失敗をできるだけなくした簡潔なプロファイルスクリプトを記述するためのもので、正常に失敗するコードを記述することで、プロファイルスクリプトの処理時にシステムスクリプトの停止が起こらないようにするものです。これらのガイドラインは、効果的に実行されることが証明されたベストプラクティスによるものです。このガイドラインは、Rhino 開発者コミュニティによる原則および推奨事項に従い適用されるものです。

* 現在のスクリプト値をユーザースクリプトのローカル変数に設定し、フェイルオーバーを空白の文字列に設定します。
* ローカル変数を検証します。ローカル変数値が空白の文字列でないことを確認します。
* 正規式とは異なり、文字列ベースの操作関数を使用します。
* 実行回数を制限しないで for ループや while ループを使用することはせず、有限回数の for ループを使用します。
* 文字列の長さは 1,300 文字、ループ回数は 50 回を超えないようにします。
* JavaScript 命令は 2,000 個を超えないようにします。Target には、スクリプトあたり 2,000 の JavaScript 命令という制限がありますが、これは、手作業で JavaScript を読んで単純に計算することはできません。例えば、Rhino は、すべての関数呼び出しと「新規」呼び出しを 100 個の命令として処理します。また、すべてのエントリデータのサイズ（URL 値など）は、命令数に影響を与える可能性があります。
* スクリプトのパフォーマンスだけでなく、組み合わされたすべてのスクリプトのパフォーマンスにも注意してください。ベストプラクティスとして、命令数の合計が 5,000 未満となるようにすることをお勧めします。命令の数を数えることは明らかではありませんが、2,000命令を超えるスクリプトは自動的に無効になることに注意する必要があります。 アクティブなプロファイルスクリプトの数は300を超えてはなりません。 各スクリプトは、mboxの呼び出しが1回行われるたびに実行されます。 必要なスクリプトだけを実行します。
* 正規表現では、先頭にドットとアスタリスクを置く（例：`/.*match/`、`/a|.*b/`）のはほとんど必要ありません。正規表現検索は、文字列のすべての位置から開始（`^` でバインドされている場合を除く）されるので、ドットとアスタリスクは既に想定されています。そうした正規表現が十分な長さ（数百文字以下）の入力データに一致すると、スクリプトの実行は中断されます。
* すべてを実行してもうまくいかない場合は、スクリプトを try ～ catch 文で囲みます。
* 次の推奨事項は、プロファイルスクリプトの複雑さを制限するのに役立ちます。 プロファイルスクリプトで実行できる命令の数は限られています。

   ベストプラクティスとして：

   * プロファイルスクリプトは小さく、できるだけ単純にします。
   * 正規式を使用しないでください。または、非常に単純な正規式のみを使用してください。 単純な式でも、評価に多くの指示を受けることができます。
   * 再帰を避けます。
   * プロファイルスクリプトをTargetに追加する前に、パフォーマンステストを行う必要があります。 すべてのプロファイルスクリプトは、すべてのmboxリクエストで実行されます。 プロファイルスクリプトが正しく実行されない場合、mboxリクエストの実行に時間がかかります。 これは、トラフィックとコンバージョンに影響を与える可能性があります。
   * プロファイルスクリプトが複雑すぎる場合は、 [応答トークンの代わりに](/help/administrating-target/response-tokens.md) 、

* See the JS Rhino engine documentation for more information: [https://www.mozilla.org/rhino/doc.html](https://www.mozilla.org/rhino/doc.html).

## プロファイルスクリプトのデバッグ {#section_E9F933DE47EC4B4E9AF2463B181CE2DA}

プロファイルスクリプトのデバッグには、次のメソッドを使用できます。

>[!NOTE]
>
>プロファイルスクリプト [!DNL console.log] はサーバー側を実行するので、プロファイルスクリプト内でプロファイル値を出力しません。

* **プロファイルスクリプトをレスポンストークンとして追加し、プロファイルスクリプトをデバッグ**

   Target で「**[!UICONTROL セットアップ]**」／「**[!UICONTROL レスポンストークン]**」の順にクリックし、デバッグしたいプロファイルスクリプトを有効にします。

   次に示すように、Target を使用してページをサイトに読み込むたびに、Target からのレスポンスの一部として、指定したプロファイルスクリプトの値が含まれます。

   ![](assets/debug_profile_script_1.png)

* **mboxTrace デバッグツールを使用してプロファイルスクリプトをデバッグ**

   このメソッドでは、**[!UICONTROL Target]**／**[!UICONTROL セットアップ]**／**[!UICONTROL 実装]**／**[!UICONTROL 認証トークンを生成]**&#x200B;をクリックして生成できる認証トークンが必要です。

   その後、2 つのパラメーター `mboxTrace=window&authorization=YOURTOKEN` をページ URL の &quot;?&quot; のうしろに加えます。

   これは、プロファイルの実行前後のスナップショットを取得できるため、レスポンストークンよりもやや詳細な情報を提供します。また、使用可能なすべてのプロファイルも表示されます。

   ![](assets/debug_profile_script_2.png)

## プロファイルスクリプトの FAQ {#section_1389497BB6D84FC38958AE43AAA6E712}

**プロファイルスクリプトを使用してデータレイヤーにあるページから情報を取得できますか？**

プロファイルスクリプトはサーバー側で実行されるので、プロファイルスクリプトを使用してページを直接読み取ることはできません。データを渡すには、mbox リクエストまたは他の[データを Target に送信する方法](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17)を使用する必要があります。データを Target に送信した後は、プロファイルスクリプトを使用して、データを mbox パラメーターまたはプロファイルパラメーターとして読み取ることができます。

## スクリプトプロファイルパラメーターに関する JavaScript リファレンス

スクリプトプロファイルパラメーターを効果的に使用するには、JavaScriptに関する単純な知識が必要です。 こセクションは、この機能を使用してわずか数分で生産性を高めるためのクイックリファレンスの役割を担います。

スクリプトプロファイルパラメーターは、「mbox/プロファイル」タブの下にあります。JavaScript の種類（文字列、整数、配列など）を返す Javascript プログラムを記述できます。

### スクリプトプロファイルパラメーターの例 {#examples}

**名前：***user. recency*

```
var dayInMillis = 3600 * 24 * 1000;
if (mbox.name == 'orderThankyouPage') {
    user.setLocal('lastPurchaseTime', new Date().getTime());
}
var lastPurchaseTime = user.getLocal('lastPurchaseTime');
if (lastPurchaseTime) {
    return ((new Date()).getTime() - lastPurchaseTime) / dayInMillis;
}
```

日の変数をミリ秒単位で作成します。mbox 名が `orderThankyouPage` の場合は、現在の日付と時間の値を取得するために、`lastPurchaseTime` と名前を付けたローカル（非表示）のユーザープロファイル属性を設定します。前回購入時間の値が読み取られており、その値が定義されている場合は、1 日のミリ秒数で割り算された、前回購入時間以降に経過した時間を返します（前回購入からの日数になります）。

**名前：***user. frequency*

```
var frequency = user.get('frequency') || 0;
if (mbox.name == 'orderThankyouPage') {
    return frequency + 1;
}
```

Creates a variable called `frequency`, initializing it to either the previous value or 0, if there was no previous value. mbox 名が `orderThankyouPage` の場合、増分された値が返されます。

**名前：***user.monetaryValue*

```
var monetaryValue = user.get('monetaryValue') || 0;
if (mbox.name == 'orderThankyouPage') {
    return monetaryValue + parseInt(mbox.param('orderTotal'));
}
```

`monetaryValue` と呼ばれる変数を作成し、特定の訪問者の現在の値を検索します（または以前の値がない場合は 0 に設定します）。mbox 名が `orderThankyouPage` の場合、以前の値と mbox に渡される `orderTotal` パラメーターの値を追加することによって、新しい金額が返されます。

**名前：** adobeQA

```
if (page.param("adobeQA"))
     return page.param("adobeQA");
else if (page.param("adobeqa"))
     return page.param("adobeqa");
else if (mbox.param("adobeQA"))
     return mbox.param("adobeQA");
```

`adobeQA` アクティビティQAの対象となるユーザーを追跡するために呼び出される変数を作成します [](/help/c-activities/c-activity-qa/activity-qa.md)。

### オブジェクトとメソッド

次のプロパティとメソッドは、スクリプトプロファイルパラメーターで参照できます。

| オブジェクトまたはメソッド | 詳細 |
| --- | --- |
| `page.url` | 現在の URL。 |
| `page.protocol` | このページに使用するプロトコル（http または https）。 |
| `page.domain` | 現在の URL ドメイン（最初のスラッシュより前のすべて）。例えば、`http://www.acme.com/categories/men_jeans?color=blu e&size=small` の `www.acme.com`。 |
| `page.query` | 現在のページのクエリ文字列。?の後のすべて。例えば、`http://www.acme.com/categories/mens_jeans?color=blue&size=small` の `blue&size=small`。 |
| `page.param(‘<par_name>’)` | `<par_name>` に示すパラメーターの値。現在の URL が Google の検索ページであり、`page.param('hl')` を入力していた場合、URL `http://www.google.com/search?hl=en& q=what+is+asdf&btnG=Google+Search` の「en」が取得されます。 |
| `page.referrer` | 上記と同じ一連の操作がリファラーとランディングに適用されます（referrer. url はリファラーの URL アドレスになります）。 |
| `landing.url`, `landing.protocol`, `landing.query`, および `landing.param` | ページのものと同様ですが、ランディングページ用です。 |
| `mbox.name` | アクティブな mbox の名前。 |
| `mbox.param(‘<par_name>’)` | アクティブな mbox 内で指定した名前の mbox パラメーター。 |
| `profile.get(‘<par_name>’)` | `<par_name>` の名前のクライアントが作成したユーザープロファイルパラメーター。例えば、ユーザーが「gender」と名前を付けたプロファイルパラメーターを設定した場合、値は「profile. gender」を使用して抽出できます。現在の訪問者に設定された「`profile.<par_name>`」の値を返します。値が設定されていない場合は null が返されます。は関数呼び出し `profile.get(<par_name>)` として修飾されています。 |
| `user.get(‘<par_name>’)` | 現在の訪問者に設定された「`user.<par_name>`」の値を返します。値が設定されていない場合は null が返されます。 |
| `user.categoryAffinity` | 最適なカテゴリーの名前が返されます。 |
| `user.categoryAffinities` | 最適なカテゴリーを持つ配列が返されます。 |
| `user.isFirstSession` | 訪問者の最初のセッションの場合は true が返されます。 |
| `user.browser` | HTTP ヘッダーにユーザーエージェントが返されます。例えば、Safari ユーザーのみを対象とするターゲット式 を作成できます。`if (user.browser != null && user.browser.indexOf('Safari') != -1) { return true; }` |

### 共通演算子


すべての標準 JavaScript 演算子が存在し、使用可能です。JavaScript 演算子は、文字列および数字（他のデータタイプも同様）に使用できます。簡単な説明：

| 演算子 | 説明 |
| --- | --- |
| `==` | 等価を示します。いずれかの辺の演算値が等しい場合に true を保持します。 |
| `!=` | 不等価を示します。いずれかの辺の演算値が等しくない場合に true を保持します。 |
| `<` | 左辺の変数が右辺の変数より小さいことを示します。変数が等しい場合は false に評価されます。 |
| `>` | 左辺の変数が右辺の変数より大きいことを示します。変数が等しい場合は false に評価されます。 |
| `<=` | `<`と同様に、変数が等しい場合を除いて true に評価されます。 |
| `>=` | `>`と同様に、変数が等しい場合を除いて true に評価されます。 |
| `&&` | 論理演算子「AND」の左右に式を書いた場合は、両辺の式がともに true の場合にのみ true になります（そうでなければ false になります）。 |
| `||` | 論理演算子「OR」の左右に式を書いた場合は、いずれかの辺の式が true の場合にのみ true になります（そうでなければ false になります）。 |
| `//` | ターゲットのブール演算子（配列ソース、配列ターゲット）のすべての要素がソースに含まれているかどうかをチェックします。<br>`//`は、ターゲット（regexp に対応）からサブ文字列を抽出し、`Array/*String*/ decode(String encoding, String regexp, String target)`にデコード します。<br>この機能では、定数の文字列値、グループ化（`condition1 || condition2) && condition3`）および正規表現（`/[^a-z]$/.test(landing.referring.url)`）の使用もサポートされています。 |

## トレーニングビデオ： プロファイルスクリプト ![チュートリアルバッジ](/help/assets/tutorial.png)

このビデオでは、プロファイルスクリプトの使用と作成に関する情報を説明します。

* プロファイルスクリプトの概要説明
* プロファイルスクリプトとプロファイルパラメーターの違いの説明
* シンプルなプロファイルスクリプトの作成
* 利用可能なオプションにアクセスするための利用可能なトークンメニューの使用
* プロファイルスクリプトの有効化と無効化

>[!VIDEO](https://video.tv.adobe.com/v/17394)
