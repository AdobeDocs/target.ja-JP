---
title: レポート
description: Customer Journey Analyticsを使用して、フラグで機能フラグレポートを表示する方法を説明します。
hide: true
exl-id: edddca99-f263-461b-a16f-b46ee7c15f6c
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 1%

---

# レポート {#reporting}

フラグは、**Customer Journey Analytics（CJA）**&#x200B;を通じてレポートを配信します。 コンソール内の「結果」タブまたは「レポート」タブはありません。代わりに、各機能フラグまたは機能グループの「**レポート**」ボタンを使用すると、その項目のスコープ付きCJA ダッシュボードが開きます。

## 前提条件 {#prerequisites}

レポートを表示する前に、次のことを確認します。

1. レポートはアプリケーション用に設定されています。[Customer Journey Analyticsを使用したレポートの設定](#setup)を参照してください。
1. 機能フラグまたは機能グループがアクティブで、データが蓄積されています。

## レポートを読む {#view-report}

機能フラグまたは機能グループのレポートを開くには：

1. コンソールで機能フラグまたは機能グループに移動します。
1. 「**レポート**」を選択します。

スコープ指定されたCustomer Journey Analytics ダッシュボードが開き、そのフラグまたは機能グループのデータが表示されます。 ダッシュボードには次のものが含まれます。

* **参加者** – 機能に適格なユーザーの合計数（バリアントとコントロールグループを組み合わせた数）
* **コントロール グループ** — コントロール グループに割り当てられたユーザーの数（既定のエクスペリエンスを受け取ったユーザー）
* **バリアントの分類** – 各バリアントとコントロール グループに登録されているユーザーの累積数
* **日別登録** – 各バリエーションとコントロールグループの登録を時系列で示す日レベルのチャート

## Customer Journey Analyticsでのレポートの設定 {#setup}

レポートを作成するには、Flags アプリケーションに接続されたCustomer Journey Analytics データセットが必要です。 お使いのアプリケーションのレポート機能を有効にするには、Flags サポートまたはAdobe担当者にお問い合わせください。

>[!NOTE]
>
>機能リクエストで渡されたIDは、プロファイルにリンクする必要はありません。 評価は実行時に行われ、イベントはCustomer Journey Analyticsに送信されます。

## 詳細については、 {#see-also}

* [最初の機能フラグを作成](create-your-first-feature-flag.md)
* [機能フラグによるA/B テスト](a-b-testing.md)
* [機能グループの作成](create-a-feature-group.md)

<!-- -->
