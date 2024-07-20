---
keywords: 訪問者プロファイル;Target 訪問者プロファイル
description: でのオーディエンスを作成して、新規訪問者または再訪問者  [!DNL Adobe Target]  カテゴリの親和性などの特定のプロファイルパラメーターを満たす訪問者をターゲットにする方法を説明します。
title: 特定のプロファイルパラメーターを満たす訪問者をターゲットにできますか？
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 35%

---

# 訪問者プロファイル

特定のプロファイルパラメーターを満たす訪問者をターゲティングするた [!DNL Adobe Target] のオーディエンスを作成します。

1. [!DNL Target] インターフェイスで、**[!UICONTROL Audiences]**/**[!UICONTROL Create Audience]** をクリックします。
1. オーディエンスに名前を付け、オプションで説明を追加します。
1. **[!UICONTROL Visitor Profile]** をオーディエンスビルダーペインにドラッグ&amp;ドロップします。

1. 「**[!UICONTROL Select]**」をクリックして、次のいずれかのオプションを選択します。

   ![target_visitor_profile 画像 ](assets/target_visitor_profile.png)

   訪問者プロファイルのパラメーターは mbox（プロファイル）を介して渡されます。新しい訪問者と再訪問者のいずれもターゲットに設定することができます。さらに、すべてのユーザーを含めることも可能です。

   * [!UICONTROL New Visitor]
   * [!UICONTROL Returning Visitor]
   * [!UICONTROL In Other Tests]
   * [!UICONTROL Not In Other Tests]
   * [!UICONTROL First Page of Session]
   * [!UICONTROL Not First Page of Session]
   * [!UICONTROL Category Affinity]

   訪問者プロファイルは、新しい `mboxPC` によって mbox 呼び出しごとにローカルエッジのメモリ内に作成されます。非アクティブ状態が 30 分間続くと、プロファイルは [!DNL Target] データベースに保存され、他のエッジからアクセスできるようになります。

   サイト訪問者がセッションの途中にログインして `3rdpartyId` ールを取得すると、`3rdPartyId` ールに関連付けられていた以前に読み込まれたすべてのプロファイル属性がすぐに使用可能になります。

   カスタムプロファイルパラメーターと `user.` パラメーターをターゲット設定できます。アクティビティのターゲット設定で使用するパラメーターを選択します。目的のパラメーターが表示されない場合、そのパラメーターは mbox によってトリガーされていません。

1. （任意）オーディエンスの追加ルールを設定します。
1. **[!UICONTROL Done]** をクリックします。

## トレーニングビデオ：オーディエンスの作成 ![ 概要バッジ ](/help/main/assets/overview.png)

このビデオでは、オーディエンスのカテゴリの使用について説明しています。

* オーディエンスの作成
* オーディエンスカテゴリの定義

>[!VIDEO](https://video.tv.adobe.com/v/17392)
