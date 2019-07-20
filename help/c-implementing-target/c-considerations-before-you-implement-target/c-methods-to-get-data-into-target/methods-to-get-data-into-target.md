---
description: ページパラメーター、ページ内プロファイル属性、スクリプトプロファイル属性、データプロバイダー、プロファイル一括更新 API、単一プロファイル更新 API、顧客属性など、データを Target に送信する様々な方法について説明します。
keywords: 実装; 実装方法; 設定; セットアップ; ページパラメーター; Tomcat; URL エンコード; ページ内プロファイル属性; mbox パラメーター; ページ内プロファイル属性; スクリプトプロファイル属性; プロファイル一括更新 API; 単一ファイル更新 API; 顧客属性; データプロバイダー
seo-description: ページパラメーター、ページ内プロファイル属性、スクリプトプロファイル属性、データプロバイダー、プロファイル一括更新 API、単一プロファイル更新 API、顧客属性など、データを Target に送信する様々な方法について説明します。
seo-title: データを Target に送信する方法
solution: 'Target '
subtopic: 導入
title: データを Target に送信する方法
topic: Standard
uuid: a6d64e39-6cdc-49fe-afe5-ecf7dcacf97d
translation-type: tm+mt
source-git-commit: 65b088292a5a1d84f1981edd804060ff28b342e0

---


# データを Target に送信する方法{#methods-to-get-data-into-target}

ページパラメーター、ページ内プロファイル属性、スクリプトプロファイル属性、データプロバイダー、プロファイル一括更新 API、単一プロファイル更新 API、顧客属性など、データを Target に送信する様々な方法について説明します。

## ページパラメーター（mbox パラメーター）{#section_5A297816173C4FE48DC4FE03860CB42B}

ページパラメーターは、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されることはありません。

ページパラメーターは、今後のターゲティングのために、訪問者のプロファイルに保管する必要がない追加のページデータを Target に送信するのに便利です。これらの値は、ページまたはユーザーが特定のページでおこなったアクションの記述に使用されます。

### 形式

ページパラメーターは、サーバー呼び出しを介して、文字列の名前と値のペアとして Target に渡されます。パラメーターの名前と値はカスタマイズできます（ただし、特定用途向けに「予約されている名前」もあります）。

例：

* `page=productPage`

* `categoryId=homeLoans`

### 使用例

**製品ページ**：閲覧された特定の製品に関する情報を送信します（Recommendations の仕組みです）

**注文の詳細**：注文データの収集のために注文 ID、orderTotal などを送信します。

**カテゴリ親和性**：特定のサイトカテゴリに対するユーザーの親和性に関するデータを構築するために、カテゴリの閲覧情報を Target に送信します。

**サードパーティデータ**：天気ターゲティングプロバイダー、アカウントデータ（例：DemandBase）、デモグラフィックデータ（例：Experian）など、サードパーティのデータソースからの情報を送信します。

### この方法のメリット

データが Target にリアルタイムで送信され、受信時と同じサーバー呼び出しで使用できます。

### 注意事項

* ページコードの更新が必要です（直接更新するか、タグ管理システムを使用します）。
* データを後続のページ／サーバー呼び出しでのターゲティングで使用する必要がある場合は、プロファイルスクリプトに変換する必要があります。
* [Internet Engineering Task Force（IETF）標準](https://www.ietf.org/rfc/rfc3986.txt)では、クエリ文字列に文字のみを含めることができます。

   Targetでは、IETFサイトで言及されているこれらの文字に加え、クエリ文字列で以下の文字を使用できます。

   `&lt; &gt; # % " { } | \\ ^ \[\] \``

   これ以外の文字はすべて URL エンコードする必要があります。The standard specifies the following format ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), as illustrated below:

   ![](assets/ietf1.png)

   または、簡略化した完全なリスト：

   ![](assets/ietf2.png)

### コードの例

targetPageParamsAll（ページのすべての mbox 呼び出しにパラメーターを追加します）：

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams（ページのグローバル mbox にパラメーターを追加します）：

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

mboxCreate コードのパラメーター：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### 関連情報のリンク

Recommendations：[ページタイプに従った実装](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

注文の確認：[コンバージョンの追跡](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

カテゴリ親和性：[カテゴリ親和性](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## ページ内プロファイル属性（in-mbox プロファイル属性）{#section_57E1C161AA7B444689B40B6F459302B6}

ページ内パラメーターは、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保管されます。

ページ内プロファイル属性を利用すると、ユーザー固有のデータを Target のプロファイルに保管し、以降のターゲティングやセグメント化に利用できます。

### 形式

ページ内プロファイル属性は、サーバー呼び出しを介して、属性名の先頭に「profile.」が追加された文字列の名前と値のペアとしてTarget に渡されます。

属性の名前と値はカスタマイズできます（ただし、特定用途向けに「予約されている名前」もあります）。

例：

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### 使用例

**ログイン情報**：ユーザーのログインに基づく、PII（個人情報）以外のデータを Target と共有します。会員ステータスや注文履歴などがこれに該当します。

**店舗情報**：ユーザーがどの場所の店舗を選んだのかを追跡します。

**過去のインタラクション**：サイトでのユーザーの過去の行動を追跡し、以降のパーソナライゼーションに生かします。

### この方法のメリット

データが Target にリアルタイムで送信され、受信時と同じサーバー呼び出しで使用できます。

### 注意事項

ページコードの更新が必要です（直接更新するか、タグ管理システムを使用します）。

属性と値はサーバー呼び出しで確認できるので、訪問者は値を確認できます。信用範囲やその他の機密情報を共有する場合は、最適な手法とはいえません。

### コードの例

targetPageParamsAll（ページのすべての mbox 呼び出しに属性を追加します）：

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams（ページのグローバル mbox に属性を追加します）：

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate コードの属性：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### 関連情報のリンク

[プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[訪問者プロファイル](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## スクリプトプロファイル属性 {#section_3E27B58C841448C38BDDCFE943984F8D}

スクリプトプロファイル属性は、Target ソリューションで定義された名前と値のペアです。値は、サーバー呼び出しごとに、Target サーバーで JavaScript スニペットが実行されることで決まります。

訪問者がオーディエンスやアクティビティメンバーシップの条件を満たしているかが評価される前に、ユーザーは、mbox 呼び出しごとに実行する簡単なコードスニペットを記述します。

### 形式

スクリプトプロファイル属性は、Target の「オーディエンス」セクションで作成します。属性の名前はどのようなものでも有効です。値は Target のユーザーが記述した JavaScript 関数によって決まります。Target でページ内プロファイル属性と区別するために、属性名の先頭には「user.」が自動的に追加されます。

コードスニペットは Rhino JS 言語で記述し、トークンやその他の値を参照できます。

### 使用例

**買い物かごの放棄**：訪問者が買い物かごにアクセスしたときに、プロファイルスクリプトを 1 に設定します。訪問者がコンバージョンに至ったら 0 にリセットします。この値が 1 の訪問者は、買い物かごに商品が入っていることになります。

**訪問数**：新たな訪問のたびに 1 ずつ加算し、訪問者のサイト再訪問頻度を追跡します。

### この方法のメリット

ページコードの更新が不要です。

オーディエンスとアクティビティメンバーシップの判断の前に実行し、単一のサーバー呼び出しでこれらのプロファイルスクリプト属性でメンバーシップに影響を与えることができます。

非常に強力です。スクリプトごとに 2,000 個の命令を実行できます。

### 注意事項

JavaScript に関する知識が必要です。

プロファイルスクリプトの実行の順番は保証されているわけではないので、相互に依存することはできません。

デバッグが困難な場合があります。

### コードの例

プロファイルスクリプトは非常に柔軟です。

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### 関連情報のリンク

[プロファイルスクリプト属性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## データプロバイダー {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

データプロバイダーは、サードパーティから Target へデータを簡単に渡すことのできる機能です。

注意：データプロバイダーは、at.js 1.3 以降を必要とします。

### 形式

`window.targetGlobalSettings.dataProviders` 設定は、データプロバイダーの配列です。

各データプロバイダーの構造について詳しくは、[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)を参照してください。

### 使用例

サードパーティから、気象予報サービス、DMP、自社の Web サービスなどのデータを収集します。このデータを利用して、オーディエンスやターゲットコンテンツを構築したり、訪問者プロファイルを充実させることができます。

### この方法のメリット

この設定では、Demandbase、BlueKai、カスタムサービスなどのサードパーティのデータプロバイダーからデータを収集し、そのデータをグローバル mbox リクエストで mbox パラメーターとして渡すことができます。

非同期および同期リクエストを介した複数のプロバイダーからのデータ収集もサポートしています。

この手法では、デフォルトのページコンテンツのちらつきを制御しながら、プロバイダーごとに個別のタイムアウトを指定し、ページのパフォーマンスへの影響を抑制することが簡単にできます。

### 注意事項

`window.targetGlobalSettings.dataProviders` に追加されたデータプロバイダーが非同期の場合は、同時並行で実行されます。訪問者 API リクエストは、待ち時間を最小限に抑えるために、`window.targetGlobalSettings.dataProviders` に追加された関数と同時に実行されます。

at.js では、データはキャッシュされません。データプロバイダーが 1 回だけデータを取得する場合は、データをキャッシュし、そのプロバイダーの関数が呼び出されたら、2 回目の呼び出しでキャッシュデータを配信できるようにする必要があります。

### コードの例

[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)にはいくつかの例が記載されています。

### 関連情報のリンク

ドキュメント：[データプロバイダー](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### トレーニングビデオ：

* [Adobe Target でのデータプロバイダーの使用](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Adobe Target でのデータプロバイダーの実装](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## プロファイル一括更新 API {#section_92AB4820A5624C669D9A1F1B6220D4FA}

API を介して、多数の訪問者のプロファイル更新を含む .csv ファイルを Target に送信します。各訪問者プロファイルでは、1 回の呼び出しで複数のページ内プロファイル属性を更新できます。

この方法は顧客属性と非常によく似ていますが、次の違いがあります。

* 顧客属性では FTP アップロードを使用しますが、Target のプロファイル一括更新 API では HTTP POST API を使用します。
* 顧客属性データは Analytics と共有できます。プロファイルの一括更新は Target のみで使用できます。
* 顧客属性の場合は、Target がまだ認識していないユーザーのプロファイルも作成できます。プロファイル一括更新 API では、既存の Target プロファイルのみが更新されます。
* 顧客属性の場合は Experience Cloud ID（ECID）を使用する必要があります。プロファイル一括更新 API では、TNT ID または `mbox3rdPartyId` が必要です。
* 送信する `mbox3rdPartyID` には、プラス記号（+）とスラッシュ（/）を含めることはできません。

### 形式

.csv ファイルでは、各訪問者を Target PCID または mboxThirdPartyId で参照する必要があります。Experience Cloud ID（ECID）には対応していません。すべてのプロファイル属性／値は、API を介して作成および更新されます。形式の詳細については、API ドキュメントを参照してください。

### 使用例

ページの実装でプロファイルデータを公開することなく、CRM やその他の社内システムに、一貫して更新して Target に送信したい有用な訪問者データを保管します。

### この方法のメリット

プロファイル属性の数に上限がありません。

サイトを介して送信されるプロファイル属性を、API を介して更新できます（その逆も可能です）。

### 注意事項

バッチファイルの容量は 50 MB 未満にする必要があります。また、1 回にアップロードできる行数は 50 万行までです。

以降のバッチで、24 時間以内にアップロードできる回数や行数に上限はありません。ただし、他のプロセスを効率的に実行するために、営業時間中は取り込みプロセスが調整される場合があります。

合間に mbox を呼び出すことなく、連続する [V2 一括更新呼び出し（](https://developers.adobetarget.com/api/#updating-profiles)）を同じ thirdPartyIds に対しておこなうと、最初の一括更新呼び出しで更新されたプロパティは上書きされます。

### コードの例

[プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)を参照してください。

### 関連情報のリンク

[プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)

## 単一プロファイル更新 API {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

プロファイル一括更新 API とほぼ同様ですが、.csv ファイルではなく、API 呼び出しで一度に 1 つの訪問者プロファイルが更新されます。

### 形式

訪問者は、Target の mboxPC または mboxThirdPartyId の値によって識別する必要があります。Experience Cloud ID（ECID）には対応していません。

### 使用例

コールセンターへの問い合わせや、ローンの獲得、店頭でのロイヤルティカードの使用、キオスクへのアクセスなど、訪問者がオフラインで行動をとったときに、Target をリアルタイムで更新します。

### この方法のメリット

プロファイル属性の数に上限がありません。

サイトを介して送信されるプロファイル属性を、API を介して更新できます（その逆も可能です）。

### 注意事項

24 時間ごとの API 呼び出しの上限は 100 万件です。

プロファイルのみが更新されます。Target がまだ認識していない潜在的なユーザーのプロファイルを作成することはできません。

### コードの例

GET および POST に対応しています。 `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### 関連情報のリンク

[プロファイルの更新](https://developers.adobetarget.com/api/#updating-profiles)

## 顧客属性 {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

顧客属性を利用すると、FTP を介して訪問者のプロファイルデータを Experience Cloud にアップロードできます。アップロード後は、データを Adobe Analytics と Adobe Target で利用できます。

Target Standard の場合は 5 個の属性、Target Premium の場合は 200 個の属性を利用できます。

### 形式

Experience Cloud ID（ECID）および属性の名前と値のペアを含む .csv ファイルは、FTP を介してアップロードするか、Experience Cloud の UI を使用して手動でアップロードします。

### 使用例

Target や Analytics など、Adobe Experience Cloud と共有したい有用な情報を、CRM やその他の社内システムに保管します。

### この方法のメリット

顧客データをアップロードすると、Target がまだ認識していない訪問者でも、その訪問者のプロファイルのエントリが Target に作成されます。

Target と Analytics で自動的にデータが同期化されます。

FTP は、API よりもシンプルな実装方法です。

### 注意事項

Target Standard の場合は 5 個の属性、Target Premium の場合は 200 個の属性を利用できます。

ページではなく、顧客属性でのみ値を更新できます。

Experience Cloud ID（ECID）の実装が必要です。

### コードの例

詳しくは、[顧客属性ソースの作成とデータファイルのアップロード](https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html)を参照してください。

### 関連情報のリンク

[顧客属性ソースの作成とデータファイルのアップロード](https://marketing.adobe.com/resources/help/en_US/mcloud/t_crs_usecase.html)