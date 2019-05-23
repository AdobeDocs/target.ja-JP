---
description: Target Standard を Adobe Scene7 と統合して、コンテンツライブラリで Digital Asset Management（DAM）を実行できます。
seo-description: Target Standard を Adobe Scene7 と統合して、コンテンツライブラリで Digital Asset Management（DAM）を実行できます。
seo-title: Scene7 設定
solution: 'Target '
subtopic: 導入
title: Scene7 設定
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: 761771a48c0ae957d455974b1f04fa3a8350a8a0

---


# Scene7 設定{#scene-settings}

Target Standard を Adobe Scene7 と統合して、コンテンツライブラリで Digital Asset Management（DAM）を実行できます。

>[!NOTE]
>
>Target を Scene7 と統合すると、Adobe Experience Cloud アセットフォルダーにアップロードされたアセットを（アクティビティの一部として）配信できるようになります。この統合によって、Scene7 にアップロードされたすべてのアセットにアクセスして、Target アクティビティで配信できるようになるわけではありません。

Scene7 アカウントがある場合は、Scene7 の資格情報を指定できます。Scene7 アカウントがない場合は、アドビの担当者までお問い合わせいただけば、お客様の Target アカウント専用の無料 Scene7 アカウントを使用してこの機能を設定いたします。このアカウントは、Target での使用のみに用途が限定されています。このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

この機能が設定されていない場合は、アクティビティ作成ワークフロー内で、スワップ画像オファーのオプションを利用することはできません。この機能が設定されたら、画像オファーを交換／変更するオプションを  [Visual Experience Composer とフォームベースの Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で利用できます。以降は、Adobe Experience Cloud からアップロードした画像を含むオファーを Target アクティビティで利用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。Experience Cloud にアップロードされた画像の公開済み URL を取得し、直接使用することや、Adobe Target のターゲット設定ワークフロー以外で使用することはできません。契約内容にあるように、この機能は許可されません。

画像のストレージの URL と、Scene7 の最終公開 URL は異なります。画像のストレージのリンクを使用してオファーを作成しないでください。作成すると、配信が機能しません。アドビのヘルプドキュメントに記載されているとおりに、画像オファーの機能を使用する必要があります。

Scene7 と統合するには、Scene7 の情報をいくつか指定する必要があります。

1. 「**[!UICONTROL セットアップ]**」／「**[!UICONTROL Scene7 設定]**」の順にクリックします。
1. 以下の Scene7 アカウント情報を指定します。

   **Scene7 の地域：** Scene7 アカウントの地域は、北米、ヨーロッパ、アジアです。

   **Scene7 アドホックフォルダー：**ターゲットフォルダーの外部に存在し、Scene7 に手動でアップロードされるコンテンツの場所

   **Scene7 電子メールアドレス：** Scene7 へのログインに使用する電子メールアドレス

   **Scene7 パスワード：** Scene7 へのログインに使用するパスワード
1. 「**[!UICONTROL 送信]**」をクリックします。
