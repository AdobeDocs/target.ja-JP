---
keywords: host;hosts;host group;troubleshooting;best practices;ubox;redirects;redirect;whitelist;allowlist;blacklist;blocklist
description: サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。
title: ホスト
topic: Standard
uuid: c7682269-4ec2-4a0f-b053-7e0ec77f4604
translation-type: tm+mt
source-git-commit: 44d9024cb9c1f6a1e28845f9545fed0d56fe176a
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 55%

---


# ホスト{#hosts}

サイトおよび実稼動前環境を整理して、管理と個別レポートを容易にします。

>[!NOTE]
>
>このトピックの情報は更新され、Target Standard/Premium 20.6.1リリース（2020年7月）で行われるUIの変更点を最新の状態に更新しました。 このトピックに示す情報のほとんどは、現在のUIに適用されます。 ただし、オプションが少し異なる場所にある場合もあります。

ホスト管理の主な目的は、非アクティブなコンテンツが誤って Web サイトに表示されるのを確実に防ぐことです。Host management also lets you separate report data by [environment](/help/administrating-target/environments.md).

ホストは任意の Web サーバー（または Web ドメイン）です。ここから、プロジェクトの任意の段階で、コンテンツを提供します。mbox を提供するいずれのホストも認識されます。

ホストは、管理を容易にするために環境にバンドルされます。例えば、数十のホストを 2 つまたは 3 つの環境に分けることができます。The preset environments include [!UICONTROL Production], [!UICONTROL Staging], and [!UICONTROL Development]. 新しい環境を追加したり、希望に応じて環境の名前を変更したりすることができます。

One environment, the default environment, is pre-named [!UICONTROL Production]. このデフォルトの環境は、名前を変更した場合でも削除できません。[!DNL Target] では、この環境で、最終的な承認済みのアクティビティとテストを扱うことを前提としています。

When an mbox request is received from new websites or domains, these new domains always appear in the [!UICONTROL Production] environment. [!UICONTROL 実稼動] 環境では設定を変更できないので、未知のサイトまたは新しいサイトでは、アクティブで準備が整ったコンテンツのみが表示されるよう保証されています。 ホスト管理では、アクティビティを有効化する前に、テスト、ステージングおよび開発環境を使って新しいアクティビティとコンテンツの質を容易に確保することもできます。

[!DNL Target] では、mboxを送受信できるホストを制限しないので、新しいサーバーやドメインが起動すると、(許可リストまたはブロックリストを設定していない限り)自動的に機能します。 このように制限がないので、未知のまたは予期できない様々なドメインで広告テストをおこなうこともできます。

ホストを管理するには、 **[!UICONTROL 管理]** / **[!UICONTROL ホスト]**&#x200B;をクリックします。

![](assets/hosts_list.png)

## Recognizing hosts {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

ホストを認識して [!UICONTROL Hosts] リストに追加するには、次の条件を満たす必要があります。

* 1 つ以上の mbox がホストに存在する
* ホスト上のページには、以下のものが含まれている必要があります。

   * 正確なat.jsまたはmbox.jsの参照
   * mbox または自動生成されたグローバル mbox の呼び出し

* mbox を含むページがブラウザーで表示できる

ページを表示した後、ホストが[!UICONTROL ホスト]リストに表示され、環境内でホストを管理したり、アクティビティおよびテストをプレビューおよび開始したりできます。

>[!NOTE] {class=&quot;- topic/note &quot;}
>
>この説明は、個人で使用する開発サーバーも対象となります。

ホストが[!UICONTROL ホスト]リストに追加された後、確実にホストが認識されるようにします。

1. **[!UICONTROL 管理]** / **[!UICONTROL ホストをクリックします]**。
1. ホストが一覧に表示されていない場合は、ブラウザーを更新します。

   By default, a newly recognized host is placed in the [!UICONTROL Production] environment. これは最も安全な環境です。その理由は、この環境に属するホストからは、非アクティブなアクティビティを表示できないからです。

1. （条件付き）移動アイコン( ![移動アイコン](/help/administrating-target/assets/icon-move.png) )をクリックして、ホストを [!UICONTROL 開発]、ステージング などの環境に移動します。

>[!NOTE]
>
>[!UICONTROL 実稼働] 環境は、名前を変更した場合でも削除できません。 この環境で、最終的なアクティブなキャンペーンとテストを扱うことを前提としています。デフォルトの環境では、非アクティブなキャンペーンの表示は許可されていません。

## Sort or search the Hosts list {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## Create allowlists that specify hosts that are authorized to send mbox calls to Target. {#allowlist}

You can create an allowlist that specifies hosts (domains) that are authorized to send mbox calls to [!DNL Target]. 呼び出しを生成するその他のすべてのホストに対しては、コメントアウト認証エラーの応答が送信されます。デフォルトでは、mbox 呼び出しを含むホストは、実稼動環境の [!DNL Target] に登録され、アクティブで承認済みのすべてのキャンペーンへのアクセス権を持ちます。If this is not the desired approach, you can instead use the allowlist to record specific hosts that are eligible to make mbox calls and receive [!DNL Target] content. すべてのホストは、「[!UICONTROL ホスト]」リストに引き続き表示されます。また、環境は引き続きこれらのホストをグループ化したり、ホストごとに異なるレベル（ホストがアクティブまたは非アクティブなキャンペーンを表示できるかどうかなど）を割り当てることができます。

許可リストを作成するには：

1. 「 [!UICONTROL ホスト] 」リストで、「ホストを **[!UICONTROL 認証]**」をクリックします。
1. 「承認済みホストをコンテンツ配信に対して **[!UICONTROL 有効にする]** 」切り替えを有効にします。
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. 「**[!UICONTROL 保存]**」をクリックします。

権限のないホストで mbox が呼び出されると、応答は `/* no display - unauthorized mbox host */` になります。

>[!IMPORTANT]
>
>**セキュリティのベストプラクティス**: のubox機能を使用する場合 [!DNL Target]、この許可リストは、リダイレクターが [ナビゲートできるドメインのリストも制御することに注意してください](/help/c-implementing-target/c-non-javascript-based-implementation/working-with-redirectors.md) 。 実装の一部としてuboxを使用する場合は、リダイレクト先のドメインを追加してください。 許可リストを指定しないと、アドビはリダイレクトURLを検証できず、悪意のあるリダイレクトから保護されます。
>
>許可リストは環境よりも優先されます。 許可リスト機能を使用する前に、すべてのホストを消去する必要があります。そうすると、許可リストで許可されているホストのみがホストリストに表示されます。 その後、ホストを必要な環境に移動できます。

場合によっては、他のサイトからのドメインが環境内に表示されることがあります。ドメインがat.jsまたはmbox.jsを呼び出す場合、リストにドメインが表示されます。 例えば、自分の Web ページのいずれかが他のユーザーのサーバーにコピーされた場合は、そのサーバーのドメインが自分の環境に表示されます。スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることもあります。

`mboxHost` が API 呼び出しで渡される場合、渡される環境のコンバージョンが記録されます。If no environment is passed, the host in the call defaults to [!UICONTROL Production].

また、「[!DNL Target]ホストに含まれない[!UICONTROL 」ボックスに目的のホストを追加して、] への mbox 呼び出しの送信を許可しない特定のホスト（ドメイン）を指定するブラックリストを作成することもできます。

>[!NOTE]
>
>認証済みホストリストは、mboxホストとデフォルトのリダイレクトホストの両方に使用されるので、Adobe TargetJavascript SDK(at.js)を使用するように承認された既存のドメインと、uboxのデフォルトのリダイレクトURLで使用されるすべてのを追加する必要があります。 ** また、今後、類似した新しい許可リストをドメインに追加する必要があります。

## Delete a host {#section_F56355BA4BC54B078A1A8179BC954632}

不要になったホストは削除することができます。

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. 「**[!UICONTROL 削除]**」をクリックして削除を確定します。

>[!NOTE]
>
>ホスト上にある mbox が設定されたページが参照されると、そのホストが再度リストされます。

## ホストのトラブルシューティング {#concept_B3D7583FA4BB480382CC7453529FE1B7}

[!DNL Adobe Target] におけるホストの管理とトラブルシューティングのベストプラクティスを紹介します。

ホストにおいて問題が発生した場合は次のトラブルシューティングのヒントを試してください。

**ホストがアカウントの mbox リストに表示されない。**

* ブラウザーで[!UICONTROL ホスト]ページを再読み込みします。
* at.jsまたはmbox.jsの参照を含め、mboxコードが正しいことを確認します。
* ホストのいずれかの mbox を参照します。ホスト上にあるどの mbox もブラウザーでレンダリングされない場合もあります。

**ランダムなドメインまたは不明なドメインが[!UICONTROL ホスト]リストに表示される。**

[!DNL Target] の呼び出しがドメインからおこなわれると、このリストにドメインが表示されます。場合によっては、スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることがあります。表示されるドメインがチームで使用していないドメインである場合は、「[!UICONTROL 削除]」をクリックして、そのドメインを削除します。

**mbox 呼び出しで /* no display - unauthorized mbox host */ が返される。**

権限のないホストで mbox が呼び出されると、応答は /* no display - unauthorized mbox host */ になります。
