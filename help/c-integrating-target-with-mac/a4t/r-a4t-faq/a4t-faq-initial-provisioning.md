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
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# 初期プロビジョニング - A4T FAQ{#initial-provisioning-a-t-faq}

このトピックには、Analytics を Target のレポートソースとしてプロビジョニングすること（A4T）に関するよくある質問に対する回答が含まれています。

## 複数ページの A4T アクティビティを設定する方法を教えてください。

基本的な複数ページの A4T ユースケースを実装するには：

* アクティビティランディング URL /ページに Target（at.js または mbox.js）と Analytics の両方の JavaScript ライブラリを実装します。両方のソリューションを実装すると、各訪問者のターゲットデータと Analytics データが結合されます。このデータは、デフォルトで設定された 90日の有効期限が切れるまで Analytics に残ります。

* 追跡すべき Analytics の指標があるサイトの残りのページに、Analytics を実装します。これらのページに Target を実装する必要はありません。これらのページにわたって取得された Analytics の指標は、前述の箇条書きにある訪問者のターゲット情報に基づき、ユーザーが最初に認定したターゲットアクティビティに自動的に統合されます。

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
