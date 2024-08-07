---
keywords: ターゲット設定、ターゲットカテゴリ、ターゲット条件、Audience Manager、カスタムプロファイルパラメーター、visitorプロファイル、カスタムユーザーパラメーター、ターゲットルール
description: カテゴリ（ブラウザー、地域、ネットワーク、オペレーティングシステム、訪問者プロファイルなど）を使用してコンテンツをターゲットにする方法を説明します。
title: オーディエンスのカテゴリとは何ですか？
feature: Audiences
exl-id: 37d6435d-4139-47c5-a871-6595e089d052
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 47%

---

# オーディエンスのカテゴリ

[!DNL Adobe Target] を使用して、複数のカテゴリ属性のいずれかをターゲットにすることができます。 各属性のターゲティングルール（またはグループ）を作成するには、目的の属性をオーディエンスビルダーペインにドラッグ&amp;ドロップします。

![ オーディエンスの属性 ](/help/main/c-target/c-audiences/assets/attributes.png)

特定のカテゴリが選択された場合、1 つ以上のターゲット条件を適用できます。例えば、地域カテゴリ内では、ルールを「市区町村=San Francisco」のように定義できます。複数の値を追加すると、OR 条件が作成されます。訪問者がこれらの値のいずれかと一致するだけで、ターゲット条件が満たされます。同じパラメーターで AND 条件を設定するには、カスタムエクスプレッションターゲットを作成します。

ルールを作成したら、「**[!UICONTROL Done]**」をクリックします。 ルールのサマリーは、ターゲットとしているレベルのターゲットリンクの隣に表示されます。

より多くの条件を追加するか、他のカテゴリ内で条件を作成することで、ルールをさらに改良できます。例えば、Googleからサイトにアクセスする、サンフランシスコ出身の Firefox ユーザーのみをターゲットにすることができます。 [!UICONTROL Geo] カテゴリをサンフランシスコからのユーザーをターゲットに、[!UICONTROL Browser] カテゴリを Firefox を使用してユーザーをターゲットに、[!UICONTROL Traffic Sources] カテゴリを [!UICONTROL From Google] からのユーザーをターゲットに設定します。 カテゴリ間で作成されたルールは、AND 演算子で結合されます。

カテゴリ間の OR 操作を含む複雑なターゲティングルールを作成するには、式のターゲットを作成します。

カスタムプロファイルパラメーターおよび `user.` パラメーターをターゲット設定することもできます。オーディエンスを追加する場合は、**[!UICONTROL Visitor Profile]** のオーディエンスをドラッグ&amp;ドロップしたあと、アクティビティのターゲット設定に使用するパラメーターを選択します。 目的のパラメーターが表示されない場合、そのパラメーターは mbox によってトリガーされていません。

検索ボックスを使用して、[!UICONTROL Audiences] リストを検索します。 オーディエンス名の一部で検索したり、特定の文字列を引用符で囲んだりすることも可能です。

オーディエンス名または最終変更日で [!UICONTROL Audience] リストを並べ替えることができます。 名前や日付で並べ替える場合は、列見出しをクリックし、昇順または降順でオーディエンスを表示するよう選択します。

## トレーニングビデオ：オーディエンスの作成 ![ チュートリアルバッジ ](/help/main/assets/tutorial.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
