---
title: 複雑なオーディエンスルール
description: 一括値の制限や、複数の条件にルールを分割する方法など、フラグ内の大規模または複雑なオーディエンスルールセットを操作する方法について説明します。
badge: label="Beta" type="Informative"
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
source-git-commit: ed3d4b67c78791454c55a2cad4908a37a4d60e26
workflow-type: tm+mt
source-wordcount: '93'
ht-degree: 3%
---
# 複雑なオーディエンスルール {#complex-rules}

## 複雑なルールに対するネストされたロジックの使用 {#nested-logic}

ネストされたロジックにより、複数のオーディエンス条件を正確なAND/OR制御と組み合わせることができます。 有効にするには：

1. 必要なオーディエンス条件を追加します。
2. オーディエンスルールセクションで&#x200B;**ネストされたロジック**&#x200B;を有効にします。
3. 各条件には番号が割り当てられます。 次の例のように、これらの数値を参照する論理式を入力します。
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

## 詳しくは、 {#see-also}

* [機能フラグと機能グループのオーディエンス](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
