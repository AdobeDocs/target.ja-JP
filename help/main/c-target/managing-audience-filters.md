---
keywords: ターゲティング；オーディエンスフィルター；オーディエンス；フィルター
description: オーディエンスフィルターを  [!DNL Adobe Target]  で使用して、特性を共有する訪問者のデータを表示する方法を説明します。
title: レポートにオーディエンスフィルターを使用できますか？
feature: Audiences
exl-id: af8dae97-4b10-4edb-a0e6-0d8daf2f0d22
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 72%

---

# レポート用のオーディエンスフィルター

[!DNL Adobe Target] のオーディエンスフィルター（またはオーディエンス）は、特定の特性または特性セットを共有する訪問者のグループです。

オーディエンスフィルターを使用して、レポート用に複数のオーディエンスを指定することができます。オーディエンスを 1 つ選択して、そのパフォーマンスを全体的なトラフィックと比較することもできます。一般的なトラフィックと比較して、様々なトラフィックソースに対して推奨結果も異なっていたかどうかを判断できます。オーディエンスフィルターは、様々なコンテンツをターゲットにする可能性のあるオーディエンスを検出するのに役立ちます。 多くの場合、1 つの推奨結果がすべてのトラフィックと適合するわけではありません。

例えば、ある検索エンジンからページに到達する訪問者が 1 つのオーディエンスとなります。また、他のオーディエンスの例としては、性別、年齢、ロケーション、登録ステータス、購入履歴、訪問者について収集可能なその他の詳細情報に基づくものがあります。オーディエンスフィルターで訪問者トラフィックを分割し、各トラフィックセグメントにおけるエクスペリエンスのパフォーマンスを比較します。

アクティビティ向けにオーディエンスフィルターを使用する計画を立てる場合、以下のガイドラインを考慮します。

* **訪問者は複数のオーディエンスに配置できます。** 2 つのオーディエンス（「新規訪問者」と「Googleからの訪問者」など）が設定され、1 人が両方の条件を満たしている場合、この訪問者はカウントされ、両方のオーディエンスで追跡されます。 その結果、各オーディエンスの訪問者を合計した数は、アクティビティの訪問者数と一致しません。
* **アクティビティを開始する前にオーディエンスを設定します。**&#x200B;オーディエンスデータを遡って取得することはできません。アクティビティの開始前にオーディエンスフィルターを設定せず、アクティビティをしばらく実行した後で使用することを決定した場合は、既に経過した時間のデータは収集されません。
* **2 ～ 4 オーディエンスで開始します。**&#x200B;トラフィックソースのような、基本情報に重点を置きます。
* **必要に応じてオーディエンスの名前を変更します。**&#x200B;アクティビティがアクティブであっても、収集された結果向けにオーディエンス名をより意味のあるものにするために、データに影響を与えることなくオーディエンスの名前を変更できます。
* **正確な値を入力します。**&#x200B;オーディエンスフィルター値の大文字と小文字は区別されます。例えば、市区町村をフィルタリングするオーディエンスを使用する場合、「Vienna」と「vienna」、「wien」と「Wien」のような、入力で想定されるスペルおよび大文字と小文字の組み合わせを含めるには、「OR」条件を使用します。
* **[!UICONTROL Audiences] リストから作成されたオーディエンスは再利用できます。**&#x200B;アクティビティの一部として作成されたオーディエンスは再利用できません。

オーディエンスの設定およびレポートに関する情報について詳しくは、以下の節を参照してください。

| タスク | トピック |
|--- |--- |
| 適切なアクティビティまたはテストを作成する。 | [アクティビティとテスト](/help/main/c-intro/target-key-concepts.md) |
| 必要に応じて、オーディエンスを作成する。 | [オーディエンスの作成](/help/main/c-target/c-audiences/create-audience.md) |
| 必要に応じて、複数のオーディエンスを組み合わせる。 | [複数のオーディエンスの結合](/help/main/c-target/combining-multiple-audiences.md) |
| アクティビティの目標と設定ページにオーディエンスを適用する。 | A/B テスト：[ 目標と設定 ](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md)<br>Automated Personalization: [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<br> エクスペリエンスのターゲット設定：[ 目標と設定 ](/help/main/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md)<br> 多変量分析テスト：[ 目標と設定 ](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md)<br>Recommendations: [Recommendations アクティビティの設定 ](/help/main/c-recommendations/t-create-recs-activity/recs-activity-settings.md)<br> アクティビティの設定：[ アクティビティの設定 ](/help/main/c-activities/activity-settings.md) |
| オーディエンスフィルターに関する情報をレポートに表示する。 | [レポート設定](/help/main/c-reports/c-report-settings/report-settings.md) |
