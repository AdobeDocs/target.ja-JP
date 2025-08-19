---
keywords: FAQ;よくある質問;analytics for target;A4T;プロビジョニング;プロビジョニング;adobe Experience Cloud
description: Analytics for [!DNL Target]  （A4T）のプロビジョニングに関するよくある質問への回答を示します。このプロビジョニングにより、Analytics for [!DNL Target]  アクティビティを使用できます。
title: A4T 初期プロビジョニングに関する情報はどこで入手できますか？
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 61%

---

# 初期プロビジョニング - A4T FAQ

このトピックには、[!DNL Adobe Analytics] のレポートソースとしての [!DNL Adobe Target] のプロビジョニング（A4T）に関するよくある質問に対する回答が含まれています。

## 複数ページの A4T アクティビティを設定する方法を教えてください。

+++回答
基本的な複数ページの A4T ユースケースを実装するには：

* アクティビティランディング URL/ページに Target と Analytics の両方のJavaScript ライブラリを実装してください。 両方のソリューションを実装すると、各訪問者のターゲットデータと Analytics データが結合されます。このデータは、デフォルトで設定された 90日の有効期限が切れるまで Analytics に残ります。

* 追跡すべき Analytics の指標があるサイトの残りのページに、Analytics を実装します。これらのページに Target を実装する必要はありません。これらのページにわたって取得された Analytics の指標は、前述の箇条書きにある訪問者のターゲット情報に基づき、ユーザーが最初に認定したターゲットアクティビティに自動的に統合されます。

+++

## [!DNL Target] アカウントで A4T が有効になっているかどうかを確認するにはどうすればよいですか？ {#section_4437D284448F4313BF953D4B6EDBACA6}

+++回答
Analytics アクティビティを定義するときは、レポートスイートを選択する前に、Analytics ユーザーアカウントと Target ユーザーアカウントの両方が必要になります。ドキュメントの説明に従って、ユーザーアカウントを設定する必要があります。[ ユーザー権限の要件 ](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083) を参照してください。

1 つ以上のExperience Cloud グループのメンバーで、Analytics と Target へのアクセス権を持ち、すべてのレポートスイートへのアクセス権を持ったら、「**[!UICONTROL Create Activity]**」の下に「Analytics を使用して A/B テストを作成する」オプションが表示されます。

プロビジョニングの問題が発生した場合は、A4T が正しくプロビジョニングされているかどうかをチェックします。

+++

## レポートスイートが読み込まれないのはなぜですか？ {#section_6CC8B2B3568A46C499895EB9811FDC2E}

+++回答
これらのいずれかの問題が発生した場合は、次をチェックしてください。

* Analytics アカウントと Target アカウントがExperience Cloudでリンクされていることを確認します。
* 一部のお客様は、同じExperience Cloud会社で複数の Analytics 会社ログインを使用しています。 複数のログインを使用する場合は、最後にログインした Analytics の会社が、統合の Target アカウントに関連付けられている会社であることを確認します。
* Experience Cloud にログインしてから数時間が経過している場合、Analytics セッションの有効期限が切れている可能性があります。一度ログアウトしてから再度ログインして、もう一度試してみます。

+++

## Target に Analytics オプションが表示されないのはなぜですか？ {#section_EDD996AFB08B4DB196DD934BE55BF48D}

+++回答
前述の「レポートスイートが読み込まれないのはなぜですか？」を参照上。 この問題の根本原因は同じです。

+++

## Analytics で A4T レポートが表示されないのはなぜですか？ {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

+++回答
前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。

+++

## [!DNL Target] 内のレポートが空なのはなぜですか？ {#section_3837104757464CB488C5A83014A669A1}

+++回答
前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。

+++
