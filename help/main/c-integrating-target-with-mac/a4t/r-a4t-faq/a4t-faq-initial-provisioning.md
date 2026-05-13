---
keywords: FAQ;よくある質問;analytics for target;A4T;プロビジョニング;プロビジョニング;adobe Experience Cloud
description: Analytics for  [!DNL Target]  （A4T）のプロビジョニングに関してよく寄せられる質問に対する回答を検索します。この質問では、 [!DNL Target]  アクティビティにAnalytics レポートを使用できます。
title: A4T初期プロビジョニングに関する情報はどこで入手できますか？
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
TQID: https://experienceleague.adobe.com/O2NhhiytLUaXarno3zH4DHi4EechHxUCMr8QifbEltw
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 474
ht-degree: 61%

---

# 初期プロビジョニング - A4T FAQ

このトピックには、[!DNL Adobe Target] （A4T）のレポートソースとして[!DNL Adobe Analytics]をプロビジョニングすることについてよく寄せられる質問に対する回答が含まれています。

## 複数ページの A4T アクティビティを設定する方法を教えてください。

+++回答
基本的な複数ページの A4T ユースケースを実装するには：

* アクティビティのランディング URL/ページに、TargetとAnalyticsの両方のJavaScript ライブラリを実装します。 両方のソリューションを実装すると、各訪問者のターゲットデータと Analytics データが結合されます。 このデータは、デフォルトで設定された 90日の有効期限が切れるまで Analytics に残ります。

* 追跡すべき Analytics の指標があるサイトの残りのページに、Analytics を実装します。 これらのページに Target を実装する必要はありません。 これらのページにわたって取得された Analytics の指標は、前述の箇条書きにある訪問者のターゲット情報に基づき、ユーザーが最初に認定したターゲットアクティビティに自動的に統合されます。

+++

## [!DNL Target] アカウントでA4Tが有効になっているかどうかを確認するにはどうすればよいですか？ {#section_4437D284448F4313BF953D4B6EDBACA6}

+++回答
Analytics アクティビティを定義するときは、レポートスイートを選択する前に、Analytics ユーザーアカウントと Target ユーザーアカウントの両方が必要になります。 ドキュメントの説明に従って、ユーザーアカウントを設定する必要があります。 [&#x200B; ユーザー権限の要件](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)を参照してください。

AnalyticsとTargetにアクセスできる1つ以上のExperience Cloud グループのメンバーであり、すべてのレポートスイートにアクセスできる場合は、**[!UICONTROL Create Activity]**&#x200B;でAnalyticsを使用してA/B テストを作成するオプションが表示されます。

プロビジョニングの問題が発生した場合は、A4T が正しくプロビジョニングされているかどうかをチェックします。

+++

## レポートスイートが読み込まれないのはなぜですか？ {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++回答
これらのいずれかの問題が発生した場合は、次をチェックしてください。

* Analytics アカウントとTarget アカウントがExperience Cloudでリンクされていることを確認します。
* 一部のお客様は、同じExperience Cloud会社で複数のAnalytics会社ログインを使用します。 複数のログインを使用する場合は、最後にログインしたAnalytics会社が、統合のTarget アカウントに関連付けられている会社であることを確認します。
* Experience Cloud にログインしてから数時間が経過している場合、Analytics セッションの有効期限が切れている可能性があります。 一度ログアウトしてから再度ログインして、もう一度試してみます。

+++

## Target に Analytics オプションが表示されないのはなぜですか？ {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++回答
前述の「レポートスイートが読み込まれないのはなぜですか？」を参照 上。 この問題の根本原因は同じです。

+++

## Analytics で A4T レポートが表示されないのはなぜですか？ {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++回答
前述の「レポートスイートが読み込まれないのはなぜですか？」を参照 してください。 この問題の根本原因は同じです。

+++

## [!DNL Target]のレポートが空なのはなぜですか？ {#section_3837104757464CB488C5A83014A669A1}

+++回答
前述の「レポートスイートが読み込まれないのはなぜですか？」を参照 してください。 この問題の根本原因は同じです。

+++
