---
keywords: 環境；トラブルシューティング；ベストプラクティス；ubox；リダイレクト；リダイレクト；ホワイトリスト；ブラックリスト；ブロックリスト 許可リストに加える
description: Adobeの環境を使用して、サイト  [!DNL Target]  実稼動前の環境を整理し、管理と環境別レポートを容易にする方法を説明します。
title: 環境の概要と使用方法
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '644'
ht-degree: 47%

---

# 環境

サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。

ホストは、管理を容易にするために環境にバンドルされます。例えば、数十のホストを 2 つまたは 3 つの環境に分けることができます。プリセット環境には、[!UICONTROL Production]、[!UICONTROL Staging]、[!UICONTROL Development] などがあります。 新しい環境を追加したり、希望に応じて環境の名前を変更したりすることができます。

デフォルトの環境である環境の 1 つは、[!UICONTROL Production] という名前が事前に付けられています。 このデフォルトの環境は、名前を変更した場合でも削除できません。[!DNL Target] では、この環境で、最終的な承認済みのアクティビティとテストを扱うことを前提としています。

新しい web サイトまたはドメインから [!DNL Target] リクエストを受信すると、これらの新しいドメインは常に [!UICONTROL Production] 環境に表示されます。 [!UICONTROL Production] 環境では設定を変更できないので、不明なサイトや新しいサイトには、アクティブで準備完了のコンテンツのみが表示されます。 ホスト管理では、アクティビティを有効化する前に、テスト、ステージングおよび開発環境を使って新しいアクティビティとコンテンツの質を容易に確保することもできます。

{{permissions-update}}

環境を管理するには、**[!UICONTROL Administration]**/**[!UICONTROL Environments]** をクリックします。

## 環境の追加 {#section_32097D0993724DF3A202D164D3F18674}

1. [!UICONTROL Environments] リストで、「**[!UICONTROL Add Environment]**」をクリックします。
1. 環境を説明する名前を指定します。
1. 環境に必要なアクティブモードを [!UICONTROL Active Activities] または [!UICONTROL Active and Inactive Activities] から指定します。

   [!UICONTROL Active and Inactive Activities] を指定すると、この環境のホストには非アクティブなアクティビティも表示されます。

1. **[!UICONTROL Save]** をクリックします。

## レポートのデフォルト環境の設定 {#section_4F8539B07C0C45E886E8525C344D5FB0}

すべてのアクティビティレポートでデフォルトとして使用する環境を選択できます。

[!UICONTROL Production] をデフォルトとして使用すると、すべての不明なホストがここに自動的に追加され、そこからのレポートデータがデフォルトのレポートビューに含まれます。 一方、「クリーン」な環境を作成すると、自分のコアサイト／ドメインのみが表示されます。

レポート用のデフォルトの環境を設定するには、以下の手順に従います。

1. [!UICONTROL Environments] リストで、星形アイコンをクリックします

>[!NOTE]
>
>[!DNL Recommendations] ユーザーは、ホストのホストグループを切り替える場合、行動データベースおよび製品データベースを再構築する必要があります。
>
>[default environment in an [!DNL Adobe Experience Platform] datastream](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank} を指定すると、この設定は [!DNL Target] の設定よりも優先されます。

## 環境の名前の変更 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. [!UICONTROL Environment] リストで、「**[!UICONTROL Edit]**」アイコンをクリックします。
1. 環境名を変更します。
1. **[!UICONTROL Save]** をクリックします。

## 環境の削除 {#section_737F8869612047868D03FC755B1223D3}

不要になった環境は削除することができます。

1. [!UICONTROL Environment] リストで、「**[!UICONTROL Delete]**」アイコンをクリックします。
1. 「**[!UICONTROL Delete]**」をクリックして削除を確認します。

>[!NOTE]
>
>[!UICONTROL Production] 環境は削除できませんが、名前は変更できます。

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"}

選択した環境（ホストグループ）の Recommendations コレクションと除外のコンテンツをプレビューできます。

{{premium-note}}

環境を使用して、カタログで使用可能な項目を用途に応じて分けることができます。 例えば、[!UICONTROL Development] と [!UICONTROL Production] の環境、異なるブランド、異なる地域にホストグループを使用できます。 デフォルトでは、カタログ検索、コレクションおよび除外のプレビュー結果はデフォルトのホストグループに基づいています。（環境フィルターを使用して、別のホストグループを選択して結果をプレビューすることもできます）。 デフォルトでは、項目の作成または更新時に環境 ID を指定しない限り、新しく追加された項目はすべてのホストグループで使用できます。

>[!NOTE]
>
>提供されるレコメンデーションは、リクエストで指定されたホストグループまたは環境 ID によって異なります。


商品が表示されていない場合は、適切なホストグループが使用されていることを確認してください。例えば、ステージング環境を使用するようにレコメンデーションを設定し、ホストグループをステージングに設定した場合、商品を表示するために、ステージング環境のコレクションを再作成する必要がある可能性があります。各環境でどの商品が利用できるかを確認するには、各環境でカタログ検索を利用します。選択した環境（ホストグループ）の Recommendations コレクションと除外のコンテンツをプレビューすることもできます。

>[!NOTE]
>選択した環境を変更した後、「検索」をクリックして、返された結果を更新する必要があります。

[!UICONTROL Environment] フィルターは、Target UI の次の場所から使用できます。

* カタログ検索（[!UICONTROL Recommendations > Catalog Search]）
* コレクションを作成ダイアログボックス（[!UICONTROL Recommendations > Collections > Create New]）
* [ コレクションを更新 ] ダイアログ ボックス（[!UICONTROL Recommendations > Collections > Edit]）
* 除外を作成ダイアログボックス（[!UICONTROL Recommendations > Exclusions > Create New]）
* [ 除外を更新 ] ダイアログ ボックス（[!UICONTROL Recommendations > Exclusions > Edit]）
