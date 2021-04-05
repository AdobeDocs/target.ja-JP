---
keywords: mbox. js faq;mbox. jsに関するよくある質問; document. write;tt.omtrdc.net; 解析ブロック
description: Adobe Targetのレガシーmbox.js実装について説明します。 Adobe Experience PlatformWeb SDK(AEP Web SDK)またはat.jsの最新バージョンに移行します。
title: ターゲットmbox.jsに関するよくある質問
feature: at.js
role: 開発者
exl-id: 0e207896-d45b-45f9-8556-6532fda72a45
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '435'
ht-degree: 73%

---

# mbox.js に関するよくある質問{#mbox-js-frequently-asked-questions}

mbox.js に関するよくある質問への回答を紹介します。

>[!IMPORTANT]
>
>**mbox.jsの提供終了**:2021年3月31日をもって、mbox.jsライブラリをサポートし [!DNL Adobe Target] なくなりました。2021年3月31日以降、mbox.jsからのすべての呼び出しが正常に失敗し、[!DNL Target]アクティビティが実行されているページにはデフォルトコンテンツが提供されます。
>
>サイトに発生する可能性のある問題を回避するため、すべてのお客様に、新しい[!DNL Adobe Experience Platform Web SDK]またはat.js JavaScriptライブラリの最新バージョンに今日までに移行することをお勧めします。 詳しくは、[概要：クライアント側web](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md)のターゲットを実装します。

## mbox.js はページ読み込み時間にどのように影響しますか。{#section_90B3B94FE0BF4B369577FCB97B67F089}

詳しくは、[at.js のメリット](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)を参照してください。

## mbox.js および document.write を使用すると Google Chrome で「Parser-blocking」警告メッセージが表示されるのはなぜですか。{#section_355A3A5BF02F42EEB8271C96EF41590A}

このコンソールメッセージは、mbox.js ファイル内で `document.write` 関数が使用される多くの状況で、Chrome を使用する場合に表示されます。これは警告メッセージで、アクティビティ設定プロセスには影響しません。

この状況を回避する最善の方法は、[Target 実装を at.js JavaScript ライブラリに移行する](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)ことです（このライブラリは `document.write` 関数を使用しません）。at.js の使用は、mbox.js の使用に比べて多くのメリットがあります。詳細については、「[at.js に関するよくある質問](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769)」を参照してください。

## Web ページで mbox が実行されないのはなぜですか。{#section_4BA5DA424B734324AAB51E4588FA50F5}

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

これらのドメインを使用する場合は、targetGlobalSettings() を使用して `cookieDomain` 設定をカスタマイズしないと、最新のブラウザーでは Cookie が保存されません。詳しくは、「[Target でのクラウドベースのインスタンスの使用](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)」を参照してください。

## Target のサーバー呼び出しが送られる tt.omtrdc.net というドメインは何ですか。{#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] は、Target のすべてのサーバー呼び出しを受信する Adobe の EDGE ネットワークの名前です。

## at.js および mbox.js で HttpOnly および Secure の Cookie フラグが使用されないのはなぜですか？{#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly はサーバー側コードでのみ設定できます。mbox などの Target Cookieは JavaScript コードで作成され保存されるので、Target では HttpOnly の Cookie フラグを使用できません。

Secure は、ページが HTTPS でロードされた場合にのみ、JavaScript で設定できます。ページが最初 HTTP でロードされる場合、JavaScript ではこのフラグを設定できません。さらに、Secure フラグを使用する場合、Cookie は HTTPS ページでのみ使用できます。

Target がユーザーを適切に追跡できるようにするために、および、Cookie が クライアント側で生成されるという理由で、Target ではこれらのフラグをどちらも使用しません。
