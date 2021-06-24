---
keywords: mbox. js faq;mbox. jsに関するよくある質問; document. write;tt.omtrdc.net; 解析ブロック
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience Platform Web SDK(AEP Web SDK)または最新バージョンのat.jsに移行します。
title: ' [!DNL Target] mbox.jsに関するよくある質問を教えてください。'
feature: at.js
role: Developer
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 75%

---

# mbox.js に関するよくある質問

mbox.js に関するよくある質問への回答を紹介します。

>[!IMPORTANT]
>
>**mbox.js のサポート終了**：2021 年 3 月 31 日（PT）をもって、[!DNL Adobe Target]mbox.js ライブラリのサポートは終了しました。 2021 年 3 月 31 日（PT）以降、mbox.js からのすべての呼び出しは失敗し、デフォルトのコンテンツを表示して [!DNL Target] アクティビティを実行しているページには影響があります。
>
>サイトで発生する可能性のある問題を回避するため、すべてのお客様にこの日までに新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに移行することをお勧めします。 詳しくは、[概要：クライアントサイド web に対する Target の実装](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)を参照してください。

## Web ページで mbox が実行されないのはなぜですか。 {#section_4BA5DA424B734324AAB51E4588FA50F5}

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

これらのドメインを使用する場合は、targetGlobalSettings() を使用して `cookieDomain` 設定をカスタマイズしないと、最新のブラウザーでは Cookie が保存されません。詳しくは、「[Target でのクラウドベースのインスタンスの使用](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)」を参照してください。

## [!DNL Target]サーバ呼び出しが送られるtt.omtrdc.netというドメインは何ですか。 {#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] は、Target のすべてのサーバー呼び出しを受信する Adobe の EDGE ネットワークの名前です。

## at.js および mbox.js で HttpOnly および Secure の Cookie フラグが使用されないのはなぜですか？ {#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly はサーバー側コードでのみ設定できます。mbox などの Target Cookieは JavaScript コードで作成され保存されるので、Target では HttpOnly の Cookie フラグを使用できません。

Secure は、ページが HTTPS でロードされた場合にのみ、JavaScript で設定できます。ページが最初 HTTP でロードされる場合、JavaScript ではこのフラグを設定できません。さらに、Secure フラグを使用する場合、Cookie は HTTPS ページでのみ使用できます。

Target がユーザーを適切に追跡できるようにするために、および、Cookie が クライアント側で生成されるという理由で、Target ではこれらのフラグをどちらも使用しません。
