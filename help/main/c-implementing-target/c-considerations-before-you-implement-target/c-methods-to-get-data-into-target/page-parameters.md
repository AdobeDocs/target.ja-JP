---
keywords: 実装；実装する；設定；設定；ページパラメータ
description: データをに取り込む [!DNL Target] ページパラメーターの使用
title: データをに取り込む方法 [!DNL Target] ページパラメーターを使用している場合
feature: Implementation
role: Developer
exl-id: a285eadc-b71e-49a8-9071-397ada283baf
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 44%

---

# ページのパラメーター

ページパラメーター（「mbox パラメーター」とも呼ばれます）は、ページコードを介して直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保存されません。

ページパラメーターは、今後のターゲティングで使用するために訪問者のプロファイルと共に保存する必要のないページデータを Target に送信する場合に役立ちます。 これらの値は、ページまたはユーザーが特定のページでおこなったアクションの記述に使用されます。

## 形式

ページパラメーターは、サーバー呼び出しを介して、文字列の名前と値のペアとして Target に渡されます。パラメーターの名前と値はカスタマイズできます（ただし、特定用途向けに「予約されている名前」もあります）。

### 例

* `page=productPage`

* `categoryId=homeLoans`

## 使用例

* **製品ページ**:閲覧された特定の製品に関する情報を送信します ( この方法はRecommendationsの仕組みです )
* **注文の詳細**:注文コレクション用に注文 ID、orderTotal などを送信する
* **カテゴリ親和性**：特定のサイトカテゴリに対するユーザーの親和性に関するデータを構築するために、カテゴリの閲覧情報を Target に送信します。
* **サードパーティデータ**：天気ターゲティングプロバイダー、アカウントデータ（例：DemandBase）、デモグラフィックデータ（例：Experian）など、サードパーティのデータソースからの情報を送信します。

## 方法の利点

データはリアルタイムで Target に送信され、同じサーバーで使用して、データが送信されるデータを呼び出すことができます。

## 注意事項

* ページコードの更新が必要です（直接更新するか、タグ管理システムを使用します）。
* 後続のページまたはサーバー呼び出しでターゲティングにデータを使用する必要がある場合は、データをプロファイルスクリプトに変換する必要があります。
* [Internet Engineering Task Force（IETF）標準](https://www.ietf.org/rfc/rfc3986.txt)では、クエリ文字列に文字のみを含めることができます。

   Target では、IETF サイトに記載されている文字に加えて、クエリ文字列で次の文字も使用できます。

   ```< > # % " { } | \ ^ [ ] ` ```

   これ以外の文字はすべて URL エンコードする必要があります。標準では、次のフォーマット ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ) です。以下の図を参照してください。

   ![](assets/ietf1.png)

   または、簡略化した完全なリスト：

   ![](assets/ietf2.png)

## コード例

targetPageParamsAll（ページのすべての mbox 呼び出しにパラメーターを追加します）：

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams（ページのグローバル mbox にパラメーターを追加します）：

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

## 関連情報へのリンク

Recommendations：[ページタイプに従った実装](https://developer.adobe.com/target/implement/recommendations/)

注文の確認：[コンバージョンの追跡](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-without-a-tag-manager/)

カテゴリ親和性：[カテゴリ親和性](/help/main/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)
