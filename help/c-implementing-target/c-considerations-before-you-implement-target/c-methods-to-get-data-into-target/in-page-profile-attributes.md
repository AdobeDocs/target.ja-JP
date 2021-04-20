---
keywords: 実装；実装；設定；設定；ページパラメータ
description: ページ内プロファイル属性を使用して、ターゲットにデータを取り込みます。
title: ページ内プロファイル属性を使用してターゲットにデータを取り込む方法を教えてください。
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
translation-type: tm+mt
source-git-commit: 20daf4510e754d77cd16be64770105932178fec5
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 56%

---

# ページ内プロファイル属性

[!DNL Adobe Target]のページ内プロファイル属性(「in-mboxプロファイル属性」とも呼ばれます)は、将来的に使用するために訪問者のプロファイルに保存されるページコードを介して直接渡される名前/値のペアです。

ページ内プロファイル属性を利用すると、ユーザー固有のデータを Target のプロファイルに保管し、以降のターゲティングやセグメント化に利用できます。

## 形式

ページ内プロファイル属性は、サーバー呼び出しを介して、属性名の先頭に「profile.」が追加された文字列の名前と値のペアとしてTarget に渡されます。

属性の名前と値はカスタマイズできます（ただし、特定用途向けに「予約されている名前」もあります）。

### 例

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## 使用例の例

* **ログイン情報**：ユーザーのログインに基づく、PII（個人情報）以外のデータを Target と共有します。このデータは、メンバーシップステータス、注文履歴などがあります。
* **店舗情報**：ユーザーがどの場所の店舗を選んだのかを追跡します。
* **過去のインタラクション**：サイトでのユーザーの過去の行動を追跡し、以降のパーソナライゼーションに生かします。

## 方法の利点

データはリアルタイムでターゲットに送信され、データが送信されるのと同じサーバーコールで使用できます。

## 注意事項

ページコードの更新が必要です（直接更新するか、タグ管理システムを使用します）。

属性と値はサーバー呼び出しで確認できるので、訪問者は値を確認できます。クレジット範囲や他の潜在的なプライベート情報などの情報を共有する場合は、この方法が最適なアプローチではない可能性があります。

## コードの例

targetPageParamsAll（ページのすべての mbox 呼び出しに属性を追加します）：

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams（ページのグローバル mbox に属性を追加します）：

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate コードの属性：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## 関連情報へのリンク

[プロファイル属性](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[訪問者プロファイル](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
