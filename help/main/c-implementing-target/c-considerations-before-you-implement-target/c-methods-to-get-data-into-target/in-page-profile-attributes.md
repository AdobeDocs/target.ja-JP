---
keywords: 実装；実装する；設定；設定；ページパラメータ
description: データをに取り込む [!DNL Target] ページ内プロファイル属性を使用する。
title: データをに取り込む方法 [!DNL Target] ページ内プロファイル属性を使用する場合
feature: Implementation
role: Developer
exl-id: c6000720-a862-4e9c-96a5-055963a79544
source-git-commit: c196b7e41101978ee029f93d5cd71c9b2d5b99f1
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 57%

---

# ページ内プロファイル属性

でのページ内プロファイル属性 [!DNL Adobe Target] （「in-mbox プロファイル属性」とも呼ばれます）は、ページコードを通じて直接渡される名前と値のペアで、今後の使用のために訪問者のプロファイルに保存されます。

ページ内プロファイル属性を利用すると、ユーザー固有のデータを Target のプロファイルに保管し、以降のターゲティングやセグメント化に利用できます。

## 形式

ページ内プロファイル属性は、サーバー呼び出しを介して、属性名の先頭に「profile.」が追加された文字列の名前と値のペアとしてTarget に渡されます。

属性の名前と値はカスタマイズできます（ただし、特定用途向けに「予約されている名前」もあります）。

### 例

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

## 使用例

* **ログイン情報**：ユーザーのログインに基づく、PII（個人情報）以外のデータを Target と共有します。このデータには、メンバーシップステータスや注文履歴などが含まれます。
* **店舗情報**：ユーザーがどの場所の店舗を選んだのかを追跡します。
* **過去のインタラクション**：サイトでのユーザーの過去の行動を追跡し、以降のパーソナライゼーションに生かします。

## 方法の利点

データはリアルタイムで Target に送信され、データが送信されるのと同じサーバー呼び出しで使用できます。

## 注意事項

ページコードの更新が必要です（直接更新するか、タグ管理システムを使用します）。

属性と値はサーバー呼び出しで確認できるので、訪問者は値を確認できます。信用範囲や、その他の潜在的な個人情報などの情報を共有する場合、この方法が最適な方法ではない可能性があります。

## コード例

targetPageParamsAll（ページのすべての mbox 呼び出しに属性を追加します）：

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams（ページのグローバル mbox に属性を追加します）：

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

mboxCreate コードの属性：

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

## 関連情報へのリンク

[プロファイル属性](/help/main/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[訪問者プロファイル](/help/main/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)
