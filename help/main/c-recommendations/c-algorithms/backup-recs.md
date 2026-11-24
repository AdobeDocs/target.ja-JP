---
keywords: レコメンデーション;代替;予備
description: Adobe [!DNL Target Recommendations]でバックアップの推奨事項を使用する方法について説明します。
title: 代替レコメンデーションの使用
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=ja#premium newtab=true" tooltip="Target Premium に含まれる機能を確認してください。"
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: 'https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 21%
---
# 代替レコメンデーションの使用 {#backup-recommendations}

>[!BEGINSHADEBOX]

**このページ：**&#x200B;では、バックアップの推奨事項が[!DNL Adobe Target Recommendations]のデザインの残りのスロットをどのように埋めるかを説明します。

>[!ENDSHADEBOX]

レコメンデーションにデザインを埋めるために十分な推奨項目がない場合、[!DNL Adobe Target]のバックアップ レコメンデーション機能には、デフォルトのコンテンツの代わりにバックアップ アルゴリズムの結果が表示されます。 バックアップの推奨事項がない場合、システムはデフォルトのコンテンツをユーザーに表示します。

>[!NOTE]
>
>**[!UICONTROL 部分デザインレンダリング]**&#x200B;および&#x200B;**[!UICONTROL バックアップ コンテンツを表示]** オプションを一緒に使用した結果を説明するマトリックスを含む詳細については、「条件を作成[&#128279;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)」の「 バックアップ コンテンツ」セクションを参照してください。

バックアップのレコメンデーション機能では、アルゴリズムのデータを使用した後に、常にサイト上で最も閲覧された項目を使用して、残りのスロットを埋めます。 例えば、5つの推奨アイテムを表示するようにデザインが構成されていますが、アルゴリズムには5つのスロットのうち2つしか入力できないような十分なデータがあります。 バックアップの推奨機能は、他の3つのスロットを一番上に表示されたアイテムで満たします。

代替レコメンデーションは、サイト全体で閲覧されている上位 500 製品からランダムに選択されます。 データが代替レコメンデーションに使用される期間は、1 週間です。

閲覧数上位 500 の結果は順番に並べられてから、20 個のバケットに分割されます。 バケットは順番に提供されますが、各バケット内の結果はランダム化されてページに戻されるため、ページを更新するユーザーには新しいランダム化された結果が表示されます。 コレクションの結合から設定された結果とフィルタリングルールが20より小さい場合、アイテムはコレクションからランダムに選択されます。

つまりこのバケット化のプロセスでは、代替レコメンデーションが次の順番で表示されます。

1. 最も閲覧された20個のアイテムがランダム化されています。
1. 次の20個の最も閲覧された項目をランダム化しました。
1. 次に閲覧された20個の項目をランダム化するなど。

バケッティングを行わないと、499番目の最も閲覧されたアイテムが表示され、次に200番目の最も閲覧されたアイテム、次に380番目の最も閲覧されたアイテムなどが表示されます。 バケット化により、最も閲覧された項目が最初に推奨されます。

アイテムがコレクションにグループ化されている場合、各条件に対して生成されたバックアップ レコメンデーションもコレクションを使用するため、コレクション内のアイテムのみがバックアップ レコメンデーションに含まれます。 グローバル除外ルールで除外された品目は、代替レコメンデーションとして提供されません。 重複している品目はレコメンデーションのバッチから削除されます。

バックアップの推奨事項はデフォルトで有効になっており、サイト上で最も人気のあるアイテムのランダムな選択でデザインの余分なスロットを埋めます。

バックアップの推奨事項の使用は、通常、初期設定の際に実装チームとの話し合いの一部として行われます。 実装後にバックアップ推奨設定を変更するには、アカウントマネージャーにお問い合わせください。

**[!UICONTROL 部分デザインレンダリング]** （[&#x200B; バックアップコンテンツ &#x200B;](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)を参照）が有効になっておらず、デザインを入力できない場合、代わりにバックアップの推奨事項（有効になっている場合）またはデフォルトのコンテンツが表示されます。
