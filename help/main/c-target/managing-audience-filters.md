---
keywords: ターゲティング；オーディエンスフィルター；オーディエンス；フィルター
description: ' [!DNL Adobe Target] のオーディエンスフィルターを使用して、特性を共有する訪問者のデータを表示する方法を説明します。'
title: レポートにオーディエンスフィルターを使用できますか？
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
TQID: https://experienceleague.adobe.com/7h16ay64Y1IVu2CbkEJny-rnGms80q8X7G6gOM1P900
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2:
  - id: b6f5758b-84f7-4943-8b05-1297a046943c
  - id: e73b329c-f712-4a22-abe7-bfbf3be6d0f9
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 477
ht-degree: 59%

---

# レポート用のオーディエンスフィルター

[!DNL Adobe Target]のオーディエンスフィルター（またはオーディエンス）は、特定の特徴または特徴のセットを共有する訪問者のグループです。

オーディエンスフィルターを使用して、レポート用に複数のオーディエンスを指定することができます。 オーディエンスを 1 つ選択して、そのパフォーマンスを全体的なトラフィックと比較することもできます。 一般的なトラフィックと比較して、様々なトラフィックソースに対して推奨結果も異なっていたかどうかを判断できます。 オーディエンスフィルターは、さまざまなコンテンツをターゲットにする可能性のあるオーディエンスを発見するのに役立ちます。 多くの場合、1 つの推奨結果がすべてのトラフィックと適合するわけではありません。

例えば、ある検索エンジンからページに到達する訪問者が 1 つのオーディエンスとなります。 また、他のオーディエンスの例としては、性別、年齢、ロケーション、登録ステータス、購入履歴、訪問者について収集可能なその他の詳細情報に基づくものがあります。 オーディエンスフィルターで訪問者トラフィックを分割し、各トラフィックセグメントにおけるエクスペリエンスのパフォーマンスを比較します。

アクティビティ向けにオーディエンスフィルターを使用する計画を立てる場合、以下のガイドラインを考慮します。

* **訪問者は複数のオーディエンスに属することができます。** 2つのオーディエンスが設定されており（例：「新規訪問者」と「Googleからの訪問者」）、両方の基準を満たす場合、この訪問者は両方のオーディエンスでカウントおよび追跡されます。 その結果、各オーディエンスの訪問者を合計した数は、アクティビティの訪問者数と一致しません。
* **アクティビティを起動する前にオーディエンスを設定します。** オーディエンスデータは、過去にさかのぼって取得することはできません。 アクティビティの開始前にオーディエンスフィルターを設定せず、アクティビティをしばらく実行した後で使用することを決定した場合は、既に経過した時間のデータは収集されません。
* **最初に2 ～ 4人のオーディエンスを作成します。** トラフィックソースのような、基本情報に重点を置きます。
* **必要に応じてオーディエンス名を変更します。** データに影響を与えることなくオーディエンスの名前を変更して、アクティビティがアクティブであっても、収集される結果に対してオーディエンス名をより意味のあるものにすることができます。
* **正確な値を入力してください。** オーディエンスフィルターの値では、大文字と小文字が区別されます。 例えば、市区町村をフィルタリングするオーディエンスを使用する場合、「Vienna」と「vienna」、「wien」と「Wien」のような、入力で想定されるスペルおよび大文字と小文字の組み合わせを含めるには、「OR」条件を使用します。
* [!UICONTROL Audiences] リストから作成された&#x200B;**オーディエンスは再利用できます。** アクティビティの一部として作成されたオーディエンスは再利用できません。

オーディエンスの設定およびレポートに関する情報について詳しくは、以下の節を参照してください。

| タスク | トピック |
|--- |--- |
| 適切なアクティビティまたはテストを作成する。 | [アクティビティとテスト](/help/main/c-intro/target-key-concepts.md) |
| 必要に応じて、オーディエンスを作成する。 | [オーディエンスの作成](/help/main/c-target/c-audiences/create-audience.md) |
| 必要に応じて、複数のオーディエンスを組み合わせる。 | [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md) |
| アクティビティの目標と設定ページにオーディエンスを適用する。 | A/B テスト：[目標と設定](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization: [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br> エクスペリエンスのターゲット設定：[目標と設定](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br>多変量テスト：[目標と設定](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>推奨事項：[推奨事項アクティビティ設定](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br> アクティビティ設定：[&#x200B; アクティビティ設定](/help/main/c-activities/activity-settings.md) |
| オーディエンスフィルターに関する情報をレポートに表示する。 | [レポート設定](/help/main/c-reports/c-report-settings/report-settings.md) |
