---
description: mbox.js に関するよくある質問への回答を紹介します。
keywords: mbox. js faq;mbox. jsに関するよくある質問; document. write;tt.omtrdc.net; 解析ブロック
seo-description: mbox.js に関するよくある質問への回答を紹介します。
seo-title: mbox.js に関するよくある質問
solution: 'Target '
subtopic: 導入
title: mbox.js に関するよくある質問
uuid: af3105ab-87d9-4dbf-a380-b72788928958
translation-type: tm+mt
source-git-commit: ac86b0131b0c65f3367c47b3a1315c37d9b9aa93

---


# mbox.js に関するよくある質問{#mbox-js-frequently-asked-questions}

mbox.js に関するよくある質問への回答を紹介します。

## mbox.js はページ読み込み時間にどのように影響しますか。{#section_90B3B94FE0BF4B369577FCB97B67F089}

詳しくは、at. jsの [利点](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits)を参照してください。

## mbox.js および document.write を使用すると Google Chrome で「Parser-blocking」警告メッセージが表示されるのはなぜですか。{#section_355A3A5BF02F42EEB8271C96EF41590A}

このコンソールメッセージは、mbox.js ファイル内で `document.write` 関数が使用される多くの状況で、Chrome を使用する場合に表示されます。これは警告メッセージで、アクティビティ設定プロセスには影響しません。

この状況を回避する最善の方法は、[Target 実装を at.js JavaScript ライブラリに移行する](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA)ことです（このライブラリは `document.write` 関数を使用しません）。at.js の使用は、mbox.js の使用に比べて多くのメリットがあります。詳細については、「[at.js に関するよくある質問](../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769)」を参照してください。

## Web ページで mbox が実行されないのはなぜですか。{#section_4BA5DA424B734324AAB51E4588FA50F5}

 のお客様は、[!DNL Target]Target でクラウドベースのインスタンスを使用してテストをおこなったり、簡単な概念実証に利用したりする場合があります。これらのドメインは、他の多くのドメインと同様に[パブリックサフィックスリスト](https://publicsuffix.org/list/public_suffix_list.dat)に含まれています。

これらのドメインを使用する場合は、targetGlobalSettings() を使用して `cookieDomain` 設定をカスタマイズしないと、最新のブラウザーでは Cookie が保存されません。詳細については、「[Target でのクラウドベースのインスタンスの使用](../../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/targeting-using-cloud-based-instances.md#concept_A2077766948F4EA081CE592D8998F566)」を参照してください。

## Target のサーバー呼び出しが送られる tt.omtrdc.net というドメインは何ですか。{#section_999C29940E8B4CAD8A957A6B1D440317}

[!DNL tt.omtrdc.net] は、Target のすべてのサーバー呼び出しを受信する Adobe の EDGE ネットワークの名前です。

## at.js および mbox.js で HttpOnly および Secure の Cookie フラグが使用されないのはなぜですか？{#section_74527E3B41B54B0A83F217C3E664ED1F}

HttpOnly はサーバー側コードでのみ設定できます。mbox などの Target Cookieは JavaScript コードで作成され保存されるので、Target では HttpOnly の Cookie フラグを使用できません。

Secure は、ページが HTTPS でロードされた場合にのみ、JavaScript で設定できます。ページが最初 HTTP でロードされる場合、JavaScript ではこのフラグを設定できません。さらに、Secure フラグを使用する場合、Cookie は HTTPS ページでのみ使用できます。

Target がユーザーを適切に追跡できるようにするために、および、Cookie が クライアント側で生成されるという理由で、Target ではこれらのフラグをどちらも使用しません。
