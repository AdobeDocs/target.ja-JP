---
title: 複雑なオーディエンスルール
description: 一括値の制限や、複数の条件にルールを分割する方法など、フラグ内の大規模または複雑なオーディエンスルールセットを操作する方法について説明します。
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 2%

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
