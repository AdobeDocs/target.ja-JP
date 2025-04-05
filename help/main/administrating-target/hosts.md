---
keywords: ホスト;ホスト;ホストグループ;トラブルシューティング;ベストプラクティス;ubox;リダイレクト;リダイレクト;ホワイトリスト;許可リスト;ブラックリスト;ブロックリスト
description: Adobe Target での管理と環境別レポートを容易に行えるように web サイトと実稼動前の環境を整理する方法について説明します。
title: ホストおよびその使用方法について
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '1027'
ht-degree: 62%

---

# ホスト

サイトと実稼動前の環境を整理し、[!DNL Adobe Target] での管理と環境別レポートを容易にします。

ホスト管理の主な目的は、非アクティブなコンテンツが誤って web サイトに表示されるのを確実に防ぐことです。ホスト管理では、レポートデータを[環境](/help/main/administrating-target/environments.md)ごとに分離することもできます。

ホストは、[!DNL Target] リクエストが行われる任意のドメインです。Web サイトでは、通常、[!DNL Target] リクエストを送信する URL の `location.hostname` プロパティです。

デフォルトでは、[!DNL Target] は、[!DNL Target] リクエストを行ったり [!DNL Target] レスポンスを受信できるホストを制限しません。新しいホストがリクエストを行うと、そのホストは自動的に機能します。This process also enables testing on different domains you don&#39;t know or can&#39;t anticipate. このデフォルトの動作を上書きする場合は、許可リストまたはブロックリストを設定して、[!DNL Target] で機能するホストを制限することができます。

{{permissions-update}}

To manage hosts, click **[!UICONTROL Administration]** > **[!UICONTROL Hosts]**.

## ホストの認識 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

To recognize a host and add it to the [!UICONTROL Hosts] list, the following conditions must be met:

* 1 つ以上の [!DNL Target] リクエストがホストに存在する必要があります。
* A page on the host must have the following:

   * 正しい mbox.js の参照
   * [!DNL Target] リクエストまたは自動生成されたグローバル [!DNL Target] リクエスト

* [!DNL Target] リクエストのあるページはブラウザーで表示する必要があります。

After the page is viewed, the host is listed in the [!UICONTROL Hosts] list, allowing you to manage it in an environment, and preview and launch activities and tests.

>[!NOTE]
>
>この説明は、個人で使用する開発サーバーも対象となります。

After a host is added to the [!UICONTROL Host] list, make sure that the host is recognized.

1. **[!UICONTROL Administration]**／**[!UICONTROL Hosts]**&#x200B;をクリックします。
1. ホストが一覧に表示されていない場合は、ブラウザーを更新します。

   デフォルトでは、新しく認識されたホストは [!UICONTROL Production] 環境に配置されます。 The [!UICONTROL Production] environment is the safest environment because it does not allow inactive activities to be viewed from these hosts.

1. （条件次第） **[!UICONTROL Move]** 動アイコン（![ 移動アイコン ](/help/main/administrating-target/assets/icon-move.png)）をクリックして、ホストを [!UICONTROL Development]、[!UICONTROL Staging]、またはその他の環境に移動します。

>[!NOTE]
>
>The [!UICONTROL Production] environment cannot be deleted, even if you rename it. なぜなら、この環境で、最終のアクティブなキャンペーンとテストを扱うことを前提としているからです。このデフォルト環境では、非アクティブなキャンペーンの表示は許可されていません。

## ホストリストの並べ替えと検索 {#section_068B23C9D8224EB78BC3B7C8580251B0}

To sort the [!UICONTROL Hosts] list, click any column header ([!UICONTROL Name], [!UICONTROL Environment], or [!UICONTROL Last Requested]) to sort the list in ascending or descending order.

To search the [!UICONTROL Hosts] list, type a search term in the [!UICONTROL Search Hosts] box.

## [!DNL Target] リクエストを [!DNL Target] に送信できるホストを指定する許可リストの作成 {#allowlist}

[!DNL Target] リクエストを [!DNL Target] に送信できるホスト（ドメイン）を指定する許可リストを作成できます。この場合、許可リストにないホストがリクエストを生成すると、許可されていない旨を記した承認エラーレスポンスが送信されます。By default, any host that contains a [!DNL Target] request registers with [!DNL Target] in the [!UICONTROL Production] environment and has access to all active and approved activities. これが期待された手法でない場合は、代わりに許可リストを使用して、[!DNL Target] リクエストの生成と [!DNL Target] コンテンツの受け取りの資格がある特定のホストを記録できます。All hosts continue to display in the [!UICONTROL Hosts] list, and environments can still be used to group these hosts and assign different levels to each, such as whether the host can see active and/or inactive activities.

許可リストを作成するには、次の手順を実行します。

1. [!UICONTROL Hosts] リストで、「**[!UICONTROL Authorize Hosts]**」をクリックします。
1. Enable the **[!UICONTROL Enable Authorized Hosts for content delivery]** toggle.
1. Add the desired hosts in the **[!UICONTROL Host contains]** box, as desired.

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. Add the desired hosts in the **[!UICONTROL Host does not contains]** box, as desired.

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. **[!UICONTROL Save]** をクリックします。

許可されていないホストで [!DNL Target] リクエストが行われた場合、`/* no display - unauthorized mbox host */` というレスポンスが返されます。

>[!IMPORTANT]
>
>**Security best practices**: If you use ubox functionality of [!DNL Target], this allowlist also controls the list of domains to which your [redirectors](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank} can navigate. 実装の一部として ubox を使用する場合は、リダイレクト先のドメインを必ず追加してください。許可リストが指定されない場合、[!DNL Adobe] は、リダイレクト URL を検証できず、悪意のあるリダイレクトの可能性から保護できません。
>
>許可リストは、環境よりも優先されます。許可リスト機能を使用する前に、すべてのホストをクリアしてください。すると、許可リストで許可されているホストのみがホストリストに表示されます。その後、ホストを必要な環境に移動できます。

場合によっては、他のサイトからのドメインが環境内に表示されることがあります。ドメインが at.js を呼び出すと、そのドメインがリストに表示されます。例えば、自分の web ページのいずれかが他のユーザーのサーバーにコピーされた場合は、そのサーバーのドメインが自分の環境に表示されます。スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることもあります。

`mboxHost` が API 呼び出しで渡される場合、渡される環境のコンバージョンが記録されます。If no environment is passed, the host in the call defaults to [!UICONTROL Production].

You can also create a denylist that specifies hosts (domains) that cannot send [!DNL Target] requests to [!DNL Target] by adding the desired hosts in the [!UICONTROL Host Does Not Contain] box.

>[!NOTE]
>
>The [!UICONTROL Authorized Hosts] list is used for both [!DNL Target] hosts and default redirect hosts. [!DNL Adobe Target] JavaScript SDK（at.js）の使用を許可されているすべての既存のドメイン、*および* ubox のデフォルトのリダイレクト URL で使用されるすべてのドメインを追加してください。今後、同様のドメインが新しく出てきた場合は、そのドメインを許可リストに追加してください。

## ホストの削除 {#section_F56355BA4BC54B078A1A8179BC954632}

不要になったホストは削除することができます。

1. From the [!UICONTROL Hosts] list, click the **[!UICONTROL Delete]** icon.
1. Click **[!UICONTROL Delete]** to confirm the deletion.

>[!NOTE]
>
>削除されたホストで、[!DNL Target] リクエストを含むページが他のユーザーによって参照された場合、そのホストは再びリストに表示されます。

## ホストのトラブルシューティング {#concept_B3D7583FA4BB480382CC7453529FE1B7}

ホストにおいて問題が発生した場合は次のトラブルシューティングのヒントを試してください。

**ホストがアカウントのリストに表示されない。**

* ブラウザーで [!UICONTROL Hosts] ページを更新します。
* at.js の参照を含め、[!DNL Target] リクエストが正しいことを確認します。
* そのホストでいずれかの [!DNL Target] リクエストを参照します。ホスト上にあるどの [!DNL Target] リクエストも、これまでブラウザーでレンダリングされたことがなかった可能性があります。

**Random or unknown domains appear in the [!UICONTROL Host] list.**

あるドメインから [!DNL Target] へのリクエストが行われると、そのドメインがリストに表示されます。場合によっては、スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることがあります。If the listed domain is not one your team uses, you can click [!UICONTROL Delete] to remove it.

**My [!DNL Target] request returns /&#42; no display - unauthorized mbox host &#42;/.**

If a [!DNL Target] request is made on an unauthorized host, the request responds with /&#42; no display - unauthorized mbox host &#42;/.
