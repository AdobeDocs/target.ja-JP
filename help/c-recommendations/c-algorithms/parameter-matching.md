---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;parameter matching
description: 項目（エンティティ）とリクエスト（APIまたはmbox）の値を比較して、Adobe TargetRecommendationsで動的にフィルターします。
title: Adobe TargetRecommendationsの動的包含ルールでのパラメーター一致によるフィルター
feature: criteria
translation-type: tm+mt
source-git-commit: b51c980d8e7db3ee574350a04f9056fe5b00a703
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 27%

---


# ![PREMIUM](/help/assets/premium.png) Parameter Matching

項目（エンティティ）とリクエスト（APIまたはmbox）内の値を比較して、動的にフィルターします。

例えば、次の例のように、「業界」ページパラメーターに一致するコンテンツ、またはデバイスのサイズや地域位置などの他のパラメーターのみをレコメンデーションします。

* 画面の幅と高さのmboxパラメーターは、モバイル訪問者のターゲットに使用でき、モバイルデバイスとアクセサリーのみを推奨します。
* 地域の地域パラメーターを使用して、冬の間にツールのレコメンデーションを返すことができます。 雪が降る地域の訪問者には、吹雪やその他の雪除け具が推奨されるが、雪が降らない地域の訪問者には推奨されない。

>[!NOTE]
>
>アクティビティが2016年10月31日より前に作成された場合、「Parameter Matching」フィルターを使用すると配信が失敗します。 この問題を回避する方法は次のとおりです。
>
>* 新しいアクティビティを作成し、条件を追加します。
>* 「パラメーターのマッチング」フィルターを含まない条件を使用します。
>* 条件から「パラメーターのマッチング」フィルターを削除します。


使用可能な演算子：

* equals
* 次と等しくない
* 次を含む
* 次を含まない
* 次の語句で始まる
* 次の語句で終わる
* 次よりも大きいか等しい
* 次よりも小さいか等しい
* 範囲内