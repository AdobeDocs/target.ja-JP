---
keywords: 訪問者プロファイル;Target 訪問者プロファイル
description: 新規訪問者や再訪問者、カテゴリーの親和性など、特定のプロファイルパラメーターを満たす訪問者をターゲットとするオーディエンスを [!DNL Adobe Target] で作成する方法について説明します。
title: 特定のプロファイルパラメーターを満たす訪問者をターゲットにできますか？
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
TQID: https://experienceleague.adobe.com/lGNJLzHHa7aBUY3ZzJUU-9I8aPNsZgye1zmnN2mGHc4
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 250
ht-degree: 36%

---

# 訪問者プロファイル

特定のプロファイルパラメーターを満たす訪問者をターゲットに、[!DNL Adobe Target]でオーディエンスを作成します。

1. [!DNL Target] インターフェイスで、「**[!UICONTROL オーディエンス]**」 > 「**[!UICONTROL オーディエンスを作成]**」をクリックします。
1. オーディエンスに名前を付け、オプションの説明を追加します。
1. **[!UICONTROL 訪問者プロファイル]**&#x200B;をオーディエンスビルダーペインにドラッグ&amp;ドロップします。

1. 「**[!UICONTROL 選択]**」をクリックして、次のいずれかのオプションを選択します。

   ![target_visitor_profile image](assets/target_visitor_profile.png)

   訪問者プロファイルのパラメーターは mbox（プロファイル）を介して渡されます。 新しい訪問者と再訪問者のいずれもターゲットに設定することができます。さらに、すべてのユーザーを含めることも可能です。

   * [!UICONTROL 新しい訪問者]
   * [!UICONTROL 再訪問者]
   * [!UICONTROL その他のテスト中]
   * [!UICONTROL 他のテストにはありません]
   * [!UICONTROL  セッションの最初のページ ]
   * [!UICONTROL  セッションの最初のページではありません]
   * [!UICONTROL  カテゴリーの親和性]

   訪問者プロファイルは、新しい `mboxPC` によって mbox 呼び出しごとにローカルエッジのメモリ内に作成されます。 非アクティブ状態が30分間続くと、プロファイルは[!DNL Target] データベースに保存され、他のエッジからアクセスできるようになります。

   サイト訪問者がセッション中にログインして`3rdpartyId`を取得すると、`3rdPartyId`に関連付けられたすべての以前に読み込まれたプロファイル属性がすぐに使用できるようになります。

   カスタムプロファイルパラメーターと `user.` パラメーターをターゲット設定できます。 アクティビティのターゲット設定で使用するパラメーターを選択します。 目的のパラメーターが表示されない場合、パラメーターはmboxによって起動されていません。

1. （オプション）オーディエンスの追加ルールを設定します。
1. 「**[!UICONTROL Done]**」をクリックします。

## トレーニングビデオ：オーディエンスの作成![概要バッジ ](/help/main/assets/overview.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
