---
keywords: environment;troubleshooting;best practices;ubox;redirects;redirect;whitelist;blacklist;blocklist;allowlist
description: サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。
title: 環境
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 3edb13b196240bb1918fc66edcc653936e32d3ef
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 68%

---


# 環境

サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。

ホストは、管理を容易にするために環境にバンドルされます。例えば、数十のホストを 2 つまたは 3 つの環境に分けることができます。The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. 新しい環境を追加したり、希望に応じて環境の名前を変更したりすることができます。

One environment, the default environment, is pre-named [!UICONTROL Production]. このデフォルトの環境は、名前を変更した場合でも削除できません。[!DNL Target] では、この環境で、最終的な承認済みのアクティビティとテストを扱うことを前提としています。

When a [!DNL Target] request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. [!UICONTROL 実稼動] 環境では設定を変更できないので、未知のサイトまたは新しいサイトでは、アクティブで準備が整ったコンテンツのみが表示されるよう保証されています。 ホスト管理では、アクティビティを有効化する前に、テスト、ステージングおよび開発環境を使って新しいアクティビティとコンテンツの質を容易に確保することもできます。

環境を管理するには、 **[!UICONTROL 管理]** / **[!UICONTROL 環境をクリックします]**。

![環境リスト](/help/administrating-target/assets/environments.png)

## 追加環境 {#section_32097D0993724DF3A202D164D3F18674}

1. [ [!UICONTROL 環境]**リストの[]**&#x200B;環境]をクリックします。
1. 環境を説明する名前を指定します。
1. 目的の環境のアクティビティモード（「[!UICONTROL アクティブなアクティビティ]」または「[!UICONTROL アクティブおよび非アクティブなアクティビティ]」）を指定します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## Set the default environment for reporting {#section_4F8539B07C0C45E886E8525C344D5FB0}

すべてのアクティビティレポートでデフォルトとして使用する環境を選択できます。

If you use [!UICONTROL Production] as your default, all unknown hosts automatically are added here and report data from there is included in the default report view. 一方、「クリーン」な環境を作成すると、自分のコアサイト／ドメインのみが表示されます。

レポート用のデフォルトの環境を設定するには、以下の手順に従います。

1. 「 [!UICONTROL 環境] 」リストで、「星形」アイコンをクリックします

>[!NOTE]
>
>[!DNL Recommendations] ユーザーは、ホストのホストグループを切り替える場合、行動データベースおよび製品データベースを再構築する必要があります。

## Change the name of an environment {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. [!UICONTROL 環境] リストで、 **[!UICONTROL 編集]** アイコンをクリックします。
1. 環境名を変更します。
1. 「**[!UICONTROL 保存]**」をクリックします。

## Delete an environment {#section_737F8869612047868D03FC755B1223D3}

不要になった環境は削除することができます。

1. [!UICONTROL 環境] リストで、 **** 削除アイコンをクリックします。
1. 「**[!UICONTROL 削除]**」をクリックして削除を確定します。

>[!NOTE]
>
>You cannot delete the [!UICONTROL Production] environment, but you can rename it.

## Recommendations：環境（ホストグループ）別にコレクションと除外をフィルター

![Premium バッジ](/help/assets/premium.png)

選択した環境（ホストグループ）の Recommendations コレクションと除外のコンテンツをプレビューできます。

>[!NOTE]
>
>Recommendations activities are available as part of the [!DNL Target] Premium solution. [!DNL Target] Premium ライセンスのない [!DNL Target] Standard では利用できません。

環境を使用して、カタログ内の使用可能な品目を用途別に分けることができます。 For example, you can use host groups for [!UICONTROL Development] and [!UICONTROL Production] environments, different brands, or different geographies. デフォルトでは、カタログ検索、コレクションおよび除外のプレビュー結果はデフォルトのホストグループに基づいています。（環境フィルターを使用して、結果をプレビューする別のホストグループを選択することもできます）デフォルトでは、項目の作成または更新時に環境 ID が指定されている場合を除き、新しく追加された項目はすべてのホストグループで使用できます。配信される Recommendations は、リクエストで指定したホストグループによって異なります。

商品が表示されていない場合は、適切なホストグループが使用されていることを確認してください。例えば、ステージング環境を使用するようにレコメンデーションを設定し、ホストグループをステージングに設定した場合、商品を表示するために、ステージング環境のコレクションを再作成する必要がある可能性があります。各環境でどの商品が利用できるかを確認するには、各環境でカタログ検索を利用します。選択した環境（ホストグループ）の Recommendations コレクションと除外のコンテンツをプレビューすることもできます。

>[!NOTE]
>選択した環境を変更した後、「検索」をクリックして、返された結果を更新する必要があります。

[!UICONTROL 環境] フィルタは、TargetUIの次の場所から使用できます。

* カタログ検索（[!UICONTROL Recommendations／カタログ検索]）
* 「コレクションを作成」ダイアログボックス（[!UICONTROL Recommendations／コレクション／新規作成]）
* 「コレクションを更新」ダイアログボックス（[!UICONTROL Recommendations／コレクション／編集]）
* 「除外を作成」ダイアログボックス（[!UICONTROL Recommendations／除外／新規作成]）
* 「除外を更新」ダイアログボックス（[!UICONTROL Recommendations／除外／編集]）