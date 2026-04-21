---
title: 徐々にロールアウトする機能を設定する
description: フラグの機能フラグにパーセンテージ ベースの段階的なロールアウトを設定する方法について説明します。
hide: true
exl-id: 1e03c533-398d-4a83-9f4a-c0419828b460
source-git-commit: fea4d9e87ad8417de9d820ee3556796fba112dc1
workflow-type: tm+mt
source-wordcount: '145'
ht-degree: 3%

---

# 徐々にロールアウトする機能を設定する {#gradual-rollout-feature}

機能フラグのパーセンテージのロールアウトは、**基本詳細** タブで設定されます。 ロールアウトの進行状況に応じて、この値を上下に調整できます。

## 動作の仕組み {#how-it-works}

ロールアウト率（25%など）を設定すると、定義したオーディエンスの割合が機能に公開されます。 残りの割合は&#x200B;**コントロールグループ**&#x200B;に配置され、デフォルトエクスペリエンスが受け取られます。

ロールアウトを拡大または縮小するには、時間の経過に伴って割合を増減できます。 パーセンテージを0%に減らすと、フラグを削除することなく、オーディエンス全員の機能が効果的にオフになります。

## 詳しくは、 {#see-also}

* [段階的な展開](../../concepts/gradual-rollout.md)
* [機能グループを設定し](set-feature-group-gradual-rollout.md)
* [最初の機能フラグを作成](create-your-first-feature-flag.md)

<!-- -->
