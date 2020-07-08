---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。
title: ホスト
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: c7664f9674234565a3657f453541095811fa5aa6
workflow-type: tm+mt
source-wordcount: '1128'
ht-degree: 26%

---


# ホスト{#hosts}

サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。

>[!NOTE]
>
>このトピックの情報は更新され、 [!DNL Target] Standard/Premium 20.6.1リリース（2020年7月）で行われるUIの変更点を最新の状態に更新しました。 このトピックに示す情報のほとんどは、現在のUIに適用されます。 ただし、オプションが少し異なる場所にある場合もあります。

ホスト管理の主な目的は、非アクティブなコンテンツが誤って Web サイトに表示されるのを確実に防ぐことです。Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

ホストは、 [!DNL Target] 要求が行われる任意のドメインです。 Webサイトでは、通常、このプロパティはリクエストを行うURLの `location.hostname` プロパティ [!DNL Target] です。

デフォルトでは、 [!DNL Target] 要求を行い、応答を受け取ることができるホスト [!DNL Target] は制限されません [!DNL Target] 。 新しいホストは、リクエストを行うと自動的に機能します。 これにより、未知の、または予期できない様々なドメインでのテストも可能になります。 このデフォルトの動作を上書きする場合は、どのホストを使用するかを制限する許可リストまたはブロックリストを設定でき [!DNL Target]ます。

ホストを管理するには、 **[!UICONTROL 管理]** / **[!UICONTROL ホスト]**&#x200B;をクリックします。

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

ホストを認識して [!UICONTROL Hosts] リストに追加するには、次の条件を満たす必要があります。

* At least one [!DNL Target] request must exist on the host
* ホスト上のページには、以下のものが含まれている必要があります。

   * 正確なat.jsまたはmbox.jsの参照
   * リク [!DNL Target] エストまたは自動生成されたグローバル [!DNL Target] リクエスト

* The page with the [!DNL Target] request must be viewed in a browser

After the page is viewed, the host is listed in the [!UICONTROL Hosts] list, allowing you to manage it in an environment, as well as preview and launch activities and tests.

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>この説明は、個人で使用する開発サーバーも対象となります。

ホストが[!UICONTROL ホスト]リストに追加された後、確実にホストが認識されるようにします。

1. **[!UICONTROL 管理]** / **[!UICONTROL ホストをクリックします]**。
1. ホストが一覧に表示されていない場合は、ブラウザーを更新します。

   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. これは最も安全な環境です。その理由は、この環境に属するホストからは、非アクティブなアクティビティを表示できないからです。

1. （条件付き） **[!UICONTROL 移動]** アイコン(移動アイコン ![)をクリックして、ホストを「](/help/administrating-target/assets/icon-move.png) DevelopmentStaging」、「Staging」、「その他の 環境」に移動します。

>[!NOTE]
>
>[!UICONTROL 実稼働] 環境は、名前を変更した場合でも削除できません。 この環境で、最終的なアクティブなキャンペーンとテストを扱うことを前提としています。デフォルトの環境では、非アクティブなキャンペーンの表示は許可されていません。

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send Target requests to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send [!DNL Target] requests to [!DNL Target]. リクエストを生成するその他すべてのホストは、コメントアウト認証エラーの応答を受け取ります。 By default, any host that contains a [!DNL Target] request registers with [!DNL Target] in the [!UICONTROL Production] environment and has access to all active and approved activities. If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make [!DNL Target] requests and receive [!DNL Target] content. All hosts will continue to display in the [!UICONTROL Hosts] list, and environments can still be used to group these hosts and assign different levels to each, such as whether the host can see active and/or inactive activities.

許可リストを作成するには：

1. 「 [!UICONTROL ホスト] 」リストで、「ホストを **[!UICONTROL 認証]**」をクリックします。
1. 「承認済みホストをコンテンツ配信に対して **[!UICONTROL 有効にする]** 」切り替えを有効にします。
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. 「**[!UICONTROL 保存]**」をクリックします。

If a [!DNL Target] request is made on an unauthorized host, the call will respond with `/* no display - unauthorized mbox host */`.

>[!IMPORTANT]
>
>**セキュリティのベストプラクティス**: のubox機能を使用する場合 [!DNL Target]、この許可リストは、リダイレクターが [ナビゲートできるドメインのリストも制御することに注意してください](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 。 実装の一部としてuboxを使用する場合は、リダイレクト先のドメインを追加してください。 許可リストを指定しないと、リダイレクトURL [!DNL Adobe] を検証できず、悪意のあるリダイレクトから保護されます。
>
>許可リストは環境よりも優先されます。 許可リスト機能を使用する前に、すべてのホストを消去する必要があります。そうすると、許可リストで許可されているホストのみがホストリストに表示されます。 その後、ホストを必要な環境に移動できます。

場合によっては、他のサイトからのドメインが環境内に表示されることがあります。ドメインがat.jsまたはmbox.jsを呼び出す場合、リストにドメインが表示されます。 例えば、自分の Web ページのいずれかが他のユーザーのサーバーにコピーされた場合は、そのサーバーのドメインが自分の環境に表示されます。スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることもあります。

`mboxHost` が API 呼び出しで渡される場合、渡される環境のコンバージョンが記録されます。If no environment is passed, the host in the call defaults to [!UICONTROL Production].

You can also create a denylist that specifies hosts (domains) than cannot send [!DNL Target] requests to [!DNL Target] by adding the desired hosts in the [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>認証済みホストリストは、 [!DNL Target] ホストとデフォルトのリダイレクトホストの両方に使用されるので、 [!DNL Adobe Target] Javascript SDK(at.js)を使用するように承認された既存のドメイン ** と、uboxのデフォルトのリダイレクトURLで使用されるすべてのドメインを追加する必要があります。 また、今後、類似した新しい許可リストをドメインに追加する必要があります。

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

不要になったホストは削除することができます。

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. 「**[!UICONTROL 削除]**」をクリックして削除を確定します。

>[!NOTE]
>
>ホスト上の [!DNL Target] 要求を含むページが参照されると、そのホストが再度リストされます。

## ホストのトラブルシューティング {#concept_B3D7583FA4BB480382CC7453529FE1B7}

ホストにおいて問題が発生した場合は次のトラブルシューティングのヒントを試してください。

**ホストがアカウントのリストに表示されません。**

* ブラウザーで[!UICONTROL ホスト]ページを再読み込みします。
* at.jsまたはmbox.jsの参照を含め、 [!DNL Target] リクエストが正しいことを確認します。
* Try browsing to one of the [!DNL Target] requests on the host. It&#39;s possible that no [!DNL Target] request on the host was ever rendered in a browser.

**ランダムなドメインまたは不明なドメインが[!UICONTROL ホスト]リストに表示される。**

A domain appears in this list if a request to [!DNL Target] is made from the domain. 場合によっては、スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることがあります。表示されるドメインがチームで使用していないドメインである場合は、「[!UICONTROL 削除]」をクリックして、そのドメインを削除します。

**リクエストが/* no display - unauthorized mbox host */を返す。[!DNL Target]**

If a [!DNL Target] request is made on an unauthorized host, the request will respond with /* no display - unauthorized mbox host */.
