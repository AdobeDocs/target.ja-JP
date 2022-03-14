---
keywords: FAQ;よくある質問;analytics for target;A4T;プロビジョニング;プロビジョニング;adobe Experience Cloud
description: 'Analytics ののプロビジョニングに関するよくある質問に対する回答を紹介します。 [!DNL Target] (A4T): [!DNL Target] アクティビティ。'
title: A4T 初期プロビジョニングの情報はどこで確認できますか？
feature: Analytics for Target (A4T)
exl-id: 4b098444-3e5b-45e3-b635-1857c2c8d183
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '477'
ht-degree: 61%

---

# 初期プロビジョニング - A4T FAQ

このトピックには、プロビジョニングに関するよくある質問に対する回答が含まれています [!DNL Adobe Analytics] レポートソースとして [!DNL Adobe Target] (A4T)。

## 複数ページの A4T アクティビティを設定する方法を教えてください。

基本的な複数ページの A4T ユースケースを実装するには：

* アクティビティのランディング URL/ページに Target と Analytics の両方の JavaScript ライブラリを実装します。 両方のソリューションを実装すると、各訪問者のターゲットデータと Analytics データが結合されます。このデータは、デフォルトで設定された 90日の有効期限が切れるまで Analytics に残ります。

* 追跡すべき Analytics の指標があるサイトの残りのページに、Analytics を実装します。これらのページに Target を実装する必要はありません。これらのページにわたって取得された Analytics の指標は、前述の箇条書きにある訪問者のターゲット情報に基づき、ユーザーが最初に認定したターゲットアクティビティに自動的に統合されます。

## A4T が [!DNL Target] アカウント？ {#section_4437D284448F4313BF953D4B6EDBACA6}

Analytics アクティビティを定義するときは、レポートスイートを選択する前に、Analytics ユーザーアカウントと Target ユーザーアカウントの両方が必要になります。ドキュメントの説明に従って、ユーザーアカウントを設定する必要があります。詳しくは、[ユーザー権限の要件](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)を参照してください。

Analytics と Target にアクセスできる 1 つ以上のExperience Cloudグループのメンバーで、すべてのレポートスイートにアクセスできる場合は、Analytics を使用して A/B テストを作成するオプションが「 」の下に表示されます。 **[!UICONTROL アクティビティを作成]**.

プロビジョニングの問題が発生した場合は、A4T が正しくプロビジョニングされているかどうかをチェックします。

## レポートスイートが読み込まれないのはなぜですか？ {#section_6CC8B2B3568A46C499895EB9811FDC2E}

これらのいずれかの問題が発生した場合は、次をチェックしてください。

* Experience Cloud内で Analytics および Target のアカウントがリンクされていることを確認します。
* 同じログイン会社内で複数の Analytics 会社ログインを使用するExperience Cloudもあります。 複数のログインを使用する場合は、最後にログインした Analytics の会社が、統合の Target アカウントに関連付けられていることを確認してください。
* Experience Cloud にログインしてから数時間が経過している場合、Analytics セッションの有効期限が切れている可能性があります。一度ログアウトしてから再度ログインして、もう一度試してみます。

## Target に Analytics オプションが表示されないのはなぜですか？ {#section_EDD996AFB08B4DB196DD934BE55BF48D}

前述の「レポートスイートが読み込まれないのはなぜですか？」を参照上. この問題の根本原因は同じです。

## Analytics で A4T レポートが表示されないのはなぜですか？ {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。

## レポートが [!DNL Target] 空？ {#section_3837104757464CB488C5A83014A669A1}

前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。
