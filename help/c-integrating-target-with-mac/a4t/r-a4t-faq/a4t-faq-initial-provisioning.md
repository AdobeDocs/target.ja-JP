---
description: このトピックには、Analytics を Target のレポートソースとしてプロビジョニングすること（A4T）に関するよくある質問に対する回答が含まれています。
keywords: FAQ;よくある質問;analytics for target;A4T;プロビジョニング;プロビジョニング;adobe Experience Cloud
seo-description: このトピックには、Analytics を Target のレポートソースとしてプロビジョニングすること（A4T）に関するよくある質問に対する回答が含まれています。
seo-title: 初期プロビジョニング - A4T FAQ
solution: 'Target '
title: 初期プロビジョニング - A4T FAQ
topic: Standard
uuid: cc80f879-ad2a-46d6-adc2-df616e8ab0b5
translation-type: tm+mt
source-git-commit: 0b4858e203c67bca85c9646e74df1111b6b5c934

---


# 初期プロビジョニング - A4T FAQ{#initial-provisioning-a-t-faq}

このトピックには、Analytics を Target のレポートソースとしてプロビジョニングすること（A4T）に関するよくある質問に対する回答が含まれています。

## 複数ページのA4Tアクティビティを設定する方法を教えてください。

基本的な複数ページのA4Tユースケースを実装するには:

* アクティビティランディングURL/ページでTarget（at. jsまたはmbox. js）とAnalyticsの両方にJavaScriptライブラリを実装します。両方のソリューションを実装すると、各訪問者のAnalyticsデータを使用してTargetデータが結び付けられます。このデータは、デフォルトの有効期限が90日に設定されるまで、Analyticsに残ります。

* Analytics指標だけを追跡するサイトの残りのページについては、Analyticsの指標をそれらのページに実装します。これらのページにTargetを実装する必要はありません。これらのページでキャプチャされたAnalytics指標は、前の箇条書きからその訪問者に添付されたTarget情報に基づいて、ユーザーが最初に修飾したTargetアクティビティに自動的に関連付けられます。

## Target アカウントで A4T が有効になっているかどうかはどうしたらわかりますか？{#section_4437D284448F4313BF953D4B6EDBACA6}

Analytics アクティビティを定義するときは、レポートスイートを選択する前に、Analytics ユーザーアカウントと Target ユーザーアカウントの両方が必要になります。ドキュメントの説明に従って、ユーザーアカウントを設定する必要があります。詳しくは、[ユーザー権限の要件](../../../c-integrating-target-with-mac/a4t/account-reqs.md#concept_4BC06CAB00BF46FF9362AFE98656B083)を参照してください。

Analytics および Target へのアクセス権のある 1 つ以上の Experience Cloud グループのメンバーになり、すべてのレポートスイートへのアクセス権を持っている場合、「**[!UICONTROL アクティビティの作成]**」で、Analytics を使用した A/B テストを作成するためのオプションを確認する必要があります。

プロビジョニングの問題が発生した場合は、A4T が正しくプロビジョニングされているかどうかをチェックします。

## レポートスイートが読み込まれないのはなぜですか？ {#section_6CC8B2B3568A46C499895EB9811FDC2E}

これらのいずれかの問題が発生した場合は、次をチェックしてください。

* Analytics と Target のアカウントが Experience Cloud でリンクされていることを確認します。
* 複数の Analytics ログインカンパニーを同じ Experience Cloud 組織名で使用している場合、最後にログインした Analytics ログインカンパニーが、統合する Target アカウントと関連付けられていることを確認します。
* Experience Cloud にログインしてから数時間が経過している場合、Analytics セッションの有効期限が切れている可能性があります。一度ログアウトしてから再度ログインして、もう一度試してみます。

## Target に Analytics オプションが表示されないのはなぜですか？ {#section_EDD996AFB08B4DB196DD934BE55BF48D}

前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。

## Analytics で A4T レポートが表示されないのはなぜですか？ {#section_FEB41E7B7E4F4F78897E4D9F021DEA59}

前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。

## Target でレポートが空なのはなぜですか？ {#section_3837104757464CB488C5A83014A669A1}

前述の「レポートスイートが読み込まれないのはなぜですか？」を参照してください。この問題の根本原因は同じです。
