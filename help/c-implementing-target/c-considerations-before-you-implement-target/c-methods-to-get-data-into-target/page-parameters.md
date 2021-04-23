---
keywords: 実装；実装；設定；設定；ページパラメータ
description: ページパラメーターを使用して [!DNL Target] にデータを取得します。
title: ページパラメーターを使用して [!DNL Target] にデータを取得する方法を教えてください。
feature: 実装
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 46%

---

# ページのパラメーター

ページパラメーター（「mboxパラメーター」とも呼ばれます）は、今後使用するために訪問者のプロファイルーに保存されないページコードを介して直接渡される名前と値のペアです。

ページパラメーターは、将来的なターゲティングでの使用のために訪問者のプロファイルと共に保存する必要のないページデータをターゲットに送信する場合に役立ちます。 これらの値は、ページまたはユーザーが特定のページでおこなったアクションの記述に使用されます。

## 形式

ページパラメーターは、サーバー呼び出しを介して、文字列の名前と値のペアとして Target に渡されます。パラメーターの名前と値はカスタマイズできます（ただし、特定用途向けに「予約されている名前」もあります）。

### 例

* `page=productPage`

* `categoryId=homeLoans`

## 使用例の例

* **製品ページ**:閲覧された特定の商品に関する情報を送信する(この方法はRecommendationsの仕組み)
* **注文の詳細**:注文収集用に注文ID、orderTotalなどを送信
* **カテゴリ親和性**：特定のサイトカテゴリに対するユーザーの親和性に関するデータを構築するために、カテゴリの閲覧情報を Target に送信します。
* **サードパーティデータ**：天気ターゲティングプロバイダー、アカウントデータ（例：DemandBase）、デモグラフィックデータ（例：Experian）など、サードパーティのデータソースからの情報を送信します。

## 方法の利点

データはリアルタイムでターゲットに送信され、データが送信されたデータを同じサーバーで呼び出して使用できます。

## 注意事項

* ページコードの更新が必要です（直接更新するか、タグ管理システムを使用します）。
* 後続のページ/サーバー呼び出しでターゲット設定に使用するデータは、プロファイルスクリプトに変換する必要があります。
* [Internet Engineering Task Force（IETF）標準](https://www.ietf.org/rfc/rfc3986.txt)では、クエリ文字列に文字のみを含めることができます。

   IETFサイトで説明されている文字に加え、ターゲットでは、クエリ文字列に次の文字を使用できます。

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   これ以外の文字はすべて URL エンコードする必要があります。標準では、次の形式( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) )を指定します。

   ![](assets/ietf1.png)

   または、簡略化した完全なリスト：

   ![](assets/ietf2.png)

## コードの例

targetPageParamsAll（ページのすべての mbox 呼び出しにパラメーターを追加します）：

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams（ページのグローバル mbox にパラメーターを追加します）：

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

mboxCreate コードのパラメーター：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

## 関連情報へのリンク

Recommendations：[ページタイプに従った実装](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

注文の確認：[コンバージョンの追跡](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

カテゴリ親和性：[カテゴリ親和性](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
