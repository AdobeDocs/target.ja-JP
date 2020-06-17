---
description: Target Standard を Adobe Dynamic Media Classic（以前の Scene7）と統合して、コンテンツライブラリで Digital Asset Management（DAM）を実行できます。
title: Dynamic Media Classic の統合 構成統合
subtopic: Getting Started
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '483'
ht-degree: 85%

---


# Dynamic Media Classic の統合{#scene-settings}

Target を Adobe Dynamic Media Classic（以前の Scene7）と統合して、コンテンツライブラリで Digital Asset Management（DAM）を実行できます。

>[!NOTE]
>
>このトピックの情報は更新され、Target Standard/Premium 20.6.1リリース（2020年7月）で行われるUIの変更点を最新の状態に更新しました。 このトピックに示す情報のほとんどは、現在のUIに適用されます。 ただし、オプションが少し異なる場所にある場合もあります。

>[!NOTE]
>
>Target を Dynamic Media Classic と統合すると、Adobe Experience Cloud アセットフォルダーにアップロードされたアセットを（アクティビティの一部として）配信できるようになります。この統合によって、Dynamic Media Classic にアップロードされたすべてのアセットにアクセスして、Target アクティビティで配信できるようになるわけではありません。

既に Dynamic Media アカウントをお持ちの場合、既存の資格情報を提供できます。アカウントをお持ちでない場合、追加費用なしで、使用制限のある Dynamic Media Classic アカウントをアドビの担当者にリクエストできます。このアカウントは、Target での使用のみに用途が限定されています。このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

この機能が設定されていない場合は、アクティビティ作成ワークフロー内で、スワップ画像オファーのオプションを利用することはできません。この機能が設定されたら、画像オファーを交換／変更するオプションを     [Visual Experience Composer とフォームベースの Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で利用できます。以降は、Adobe Experience Cloud からアップロードした画像を含むオファーを Target アクティビティで利用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。Experience Cloud にアップロードされた画像の公開済み URL を取得し、直接使用することや、Adobe Target のターゲット設定ワークフロー以外で使用することはできません。契約内容にあるように、この機能は許可されません。

Dynamic Mediaからの画像のストレージ URL と最終公開 URL は異なります。画像のストレージのリンクを使用してオファーを作成しないでください。作成すると、配信が機能しません。アドビのヘルプドキュメントに記載されているとおりに、画像オファーの機能を使用する必要があります。

Dynamic Mediaクラシック(Scene7)と統合するには、次の情報を指定する必要があります。

1. **[!UICONTROL 管理]** / **[!UICONTROL Scene7設定をクリックします]**。

   ![Scene7ページ](/help/administrating-target/assets/scene7.png)

1. 以下の Dynamic Media Classic アカウント情報を指定します。

   **地域：** Dynamic Media アカウントの地域は、北米、ヨーロッパ、アジアです。

   **アドホックフォルダー：**&#x200B;ターゲットフォルダーの外部に存在し、Dynamic Media に手動でアップロードされるコンテンツの場所。

   **電子メールアドレス：** Dynamic Media Classic（Scene7）へのログインに使用される電子メールアドレス。

   **パスワード：** Dynamic Media Classic（Scene7）へのログインに使用されるパスワード。

1. 「**[!UICONTROL 送信]**」をクリックします。
