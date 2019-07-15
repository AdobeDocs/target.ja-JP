---
description: Target Standardは、Adobe Dynamic Media Classic（以前のScene7）と統合して、コンテンツライブラリでDigital Asset Management（DAM）を提供できます。
seo-description: Target Standardは、Adobe Dynamic Media Classic（以前のScene7）と統合して、コンテンツライブラリでDigital Asset Management（DAM）を提供できます。
seo-title: Dynamic Media Classicの統合
solution: 'Target '
subtopic: 導入
title: Dynamic Media Classicの統合
topic: Standard
uuid: 4b06a3ed-0e87-4e49-874f-2e479324f81c
translation-type: tm+mt
source-git-commit: c6a59843c80017e6f072f65ffad822fe198ebb55

---


# Dynamic Media Classic integration{#scene-settings}

Target Standardは、Adobe Dynamic Media Classic（以前のScene7）と統合して、コンテンツライブラリでDigital Asset Management（DAM）を提供できます。

>[!NOTE]
>
>TargetをDynamic Media Classicと統合すると、Adobe Experience Cloudアセットフォルダーにアップロードされたアセットを（アクティビティの一部として）配信できます。この統合では、Dynamic Media Classicでアップロードされたすべてのアセットにアクセスして、Targetアクティビティで配信することはできません。

既にダイナミックメディアアカウントを持っている場合は、既存の資格情報を提供できます。アカウントをお持ちでない場合は、アドビの担当者から追加料金なしで、制限付きのDynamic Media Classicアカウントをリクエストできます。このアカウントは、Target での使用のみに用途が限定されています。このサービスは、ワークフローに画像の入れ替え機能が必要なお客様向けのものです。

この機能が設定されていない場合は、アクティビティ作成ワークフロー内で、スワップ画像オファーのオプションを利用することはできません。この機能が設定されたら、画像オファーを交換／変更するオプションを     [Visual Experience Composer とフォームベースの Experience Composer](../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D) の両方で利用できます。以降は、Adobe Experience Cloud からアップロードした画像を含むオファーを Target アクティビティで利用できます。

アクティビティの作成中に、オファーやカスタムコードで公開画像 URL を直接参照したい場合は、各自の Web サーバーに画像を展開し、コードで独自の URL を使用する必要があります。Experience Cloud にアップロードされた画像の公開済み URL を取得し、直接使用することや、Adobe Target のターゲット設定ワークフロー以外で使用することはできません。契約内容にあるように、この機能は許可されません。

ダイナミックメディアからの画像の保存URLと最終公開URLは、配信として画像のストレージリンクを使用して作成することはできません。この場合、配信として画像のストレージリンクを使用することはできません。アドビのヘルプドキュメントに記載されているとおりに、画像オファーの機能を使用する必要があります。

Dynamic Media Classic（Scene7）と統合するには、次の情報を指定する必要があります。

1. 「**[!UICONTROL セットアップ]**」／「**[!UICONTROL Scene7 設定]**」の順にクリックします。
1. 次のDynamic Media Classicアカウント情報を指定します。

   **地域:** Dynamic Mediaアカウントの領域:北米、ヨーロッパ、アジア。

   **アドホックフォルダー:** ターゲットフォルダーの外部に存在し、動的メディアに手動でアップロードされるコンテンツの場所です。

   **電子メールアドレス:** Dynamic Media Classic（Scene7）へのログインに使用する電子メールアドレス。

   **パスワード:** Dynamic Media Classic（Scene7）へのログインに使用するパスワードです。
1. 「**[!UICONTROL 送信]**」をクリックします。
