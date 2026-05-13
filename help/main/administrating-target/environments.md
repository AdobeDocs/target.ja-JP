---
keywords: 環境；トラブルシューティング；ベストプラクティス；ubox；リダイレクト；リダイレクト；ホワイトリスト；ブラックリスト；ヘルプブロックリストに加える
description: Adobe [!DNL Target] の環境を使用して、サイトとプリプロダクション環境を整理し、管理を容易にし、レポートを分離する方法を説明します。
title: 環境とその使用方法を教えてください。
feature: Administration & Configuration
role: Admin
exl-id: 820a116a-15f9-4ba0-94f3-8e35aa0f90da
TQID: https://experienceleague.adobe.com/ve3zhtylLWwRv890FaptsA9shmINkioM6-Yrq-nmmm0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 658
ht-degree: 47%

---

# 環境

サイトおよび本番前の環境を整理して、管理と個別レポートを容易にします。

ホストは、管理を容易にするために環境にバンドルされます。 例えば、数十のホストを 2 つまたは 3 つの環境に分けることができます。 プリセット環境には、[!UICONTROL Production]、[!UICONTROL Staging]および[!UICONTROL Development]が含まれます。 新しい環境を追加したり、希望に応じて環境の名前を変更したりすることができます。

既定の環境である1つの環境には、事前に[!UICONTROL Production]という名前が付けられています。 このデフォルトの環境は、名前を変更した場合でも削除できません。 [!DNL Target] では、この環境で、最終的な承認済みのアクティビティとテストを扱うことを前提としています。

新しいweb サイトまたはドメインから[!DNL Target] リクエストを受信すると、これらの新しいドメインは常に[!UICONTROL Production]環境に表示されます。 [!UICONTROL Production]環境の設定を変更できないため、不明または新しいサイトには、アクティブで準備が整っているコンテンツのみが表示されることが保証されます。 ホスト管理では、アクティビティを有効化する前に、テスト、ステージングおよび開発環境を使って新しいアクティビティとコンテンツの質を容易に確保することもできます。

{{permissions-update}}

環境を管理するには、**[!UICONTROL Administration]** > **[!UICONTROL Environments]**&#x200B;をクリックします。

## 環境の追加 {#section_32097D0993724DF3A202D164D3F18674}

1. [!UICONTROL Environments] リストから、**[!UICONTROL Add Environment]**&#x200B;をクリックします。
1. 環境を説明する名前を指定します。
1. 環境の目的のアクティブモードを指定してください：[!UICONTROL Active Activities]または[!UICONTROL Active and Inactive Activities]。

   [!UICONTROL Active and Inactive Activities]を指定すると、この環境のホストにも非アクティブなアクティビティが表示されます。

1. **[!UICONTROL Save]** をクリックします。

## レポート用のデフォルト環境の設定 {#section_4F8539B07C0C45E886E8525C344D5FB0}

すべてのアクティビティレポートでデフォルトとして使用する環境を選択できます。

[!UICONTROL Production]をデフォルトとして使用すると、すべての不明なホストがここに自動的に追加され、そこからのレポートデータがデフォルトのレポートビューに含まれます。 一方、「クリーン」な環境を作成すると、自分のコアサイト／ドメインのみが表示されます。

レポート用のデフォルトの環境を設定するには、以下の手順に従います。

1. [!UICONTROL Environments] リストから、星アイコンをクリックします

>[!NOTE]
>
>[!DNL Recommendations] ユーザーは、ホストのホストグループを切り替える場合、行動データベースおよび製品データベースを再構築する必要があります。
>
> [!DNL Adobe Experience Platform]  データストリーム [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=en#target){target=_blank}で デフォルト環境を指定した場合、この設定は[!DNL Target]の設定を上書きします。

## 環境の名前の変更 {#section_9F5F94285F8E495E9CE69810CE94CA08}

1. [!UICONTROL Environment] リストから、**[!UICONTROL Edit]** アイコンをクリックします。
1. 環境名を変更します。
1. **[!UICONTROL Save]** をクリックします。

## 環境の削除 {#section_737F8869612047868D03FC755B1223D3}

不要になった環境は削除することができます。

1. [!UICONTROL Environment] リストから、**[!UICONTROL Delete]** アイコンをクリックします。
1. 「**[!UICONTROL Delete]**」をクリックして、削除を確定します。

>[!NOTE]
>
>[!UICONTROL Production]環境は削除できませんが、名前を変更できます。

## [!BADGE Premium]{type=Positive url="/help/main/c-intro/intro.md#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"}の推奨事項：環境（ホストグループ）別にコレクションと除外をフィルタリング

選択した環境（ホストグループ）のレコメンデーションコレクションと除外のコンテンツをプレビューできます。

{{premium-note}}

環境を使用すると、カタログ内の使用可能なアイテムを様々な用途で分離できます。 例えば、[!UICONTROL Development]および[!UICONTROL Production]環境、異なるブランド、または異なる地域のホストグループを使用できます。 デフォルトでは、カタログ検索、コレクションおよび除外のプレビュー結果はデフォルトのホストグループに基づいています。 （環境フィルターを使用して、結果をプレビューする別のホストグループを選択することもできます）。 デフォルトでは、新しく追加された項目は、項目の作成または更新時に環境IDが指定されていない限り、すべてのホストグループで使用できます。

>[!NOTE]
>
>配信される推奨事項は、リクエストで指定されたホストグループまたは環境IDによって異なります。


商品が表示されていない場合は、適切なホストグループが使用されていることを確認してください。 例えば、ステージング環境を使用するようにレコメンデーションを設定し、ホストグループをステージングに設定した場合、商品を表示するために、ステージング環境のコレクションを再作成する必要がある可能性があります。 各環境でどの商品が利用できるかを確認するには、各環境でカタログ検索を利用します。 選択した環境（ホストグループ）のレコメンデーションコレクションと除外のコンテンツをプレビューすることもできます。

>[!NOTE]
>選択した環境を変更した後、「検索」をクリックして、返された結果を更新する必要があります。

[!UICONTROL Environment] フィルターは、Target UIの次の場所から使用できます。

* カタログ検索（[!UICONTROL Recommendations > Catalog Search]）
* コレクションを作成ダイアログ ボックス （[!UICONTROL Recommendations > Collections > Create New]）
* コレクションを更新ダイアログ ボックス （[!UICONTROL Recommendations > Collections > Edit]）
* 除外を作成ダイアログ ボックス （[!UICONTROL Recommendations > Exclusions > Create New]）
* 除外を更新ダイアログボックス （[!UICONTROL Recommendations > Exclusions > Edit]）
