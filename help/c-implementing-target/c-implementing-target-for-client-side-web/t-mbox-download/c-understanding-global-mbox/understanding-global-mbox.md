---
keywords: global mbox;implement mbox.js;implement at.js
description: グローバルmboxについて取り上げます。グローバルmboxとは、Adobe Targetの実装の各Webページの上部で行われる単一のサーバー呼び出しを参照するために使用される名前です。
title: グローバル mbox について
feature: at.js
translation-type: tm+mt
source-git-commit: 88f6e4c6ad168e4f9ce69aa6618d8641b466e28a
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 86%

---


# グローバル mbox について

グローバル mbox について説明します。グローバル mbox とは、[!DNL Adobe Target] 実装の各 Web ページの最上部でおこなわれる単一のサーバーコールを参照するために使用される名前です。

デフォルトでは、グローバル mbox は、`target-global-mbox` という名前が付いています。必要に応じて、アカウント用に名前を変更できます。

標準の mbox（非グローバル mbox）とグローバル mbox には、次のようないくつかの違いがあります。

| 標準の mbox | グローバル mbox |
|--- |--- |
| 標準の mbox は、通常、`<DIV>` タグでコンテンツを囲みます。 | グローバル mbox は、「空」で、コンテンツを囲みません。 |
| 1 つのアクティビティのみからのコンテンツは、1 つの標準の mbox に配信できます。 | 複数のアクティビティからのコンテンツは、1 つのグローバル mbox への 1 回の応答で配信できます。 |

複数のアクティビティがグローバル mbox または複数の標準 mbox を使用して配信される場合、[!DNL Target] は、アクティビティがどちらで Web ページに配信されたかによって[優先度を判別](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F)します。

追加のページレベルのデータは、[!DNL Target] 関数を使用することで、グローバル mbox と共に `targetPageParams` に送信できます。これは、mbox パラメーターの機能と同様です。詳しくは、「[グローバル mbox にパラメーターを渡す](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5)」を参照してください。
