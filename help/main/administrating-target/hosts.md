---
keywords: ホスト;ホスト;ホストグループ;トラブルシューティング;ベストプラクティス;ubox;リダイレクト;リダイレクト;ホワイトリスト;許可リスト;ブラックリスト;ブロックリスト
description: Adobe Target での管理と環境別レポートを容易に行えるように web サイトと実稼動前の環境を整理する方法について説明します。
title: ホストおよびその使用方法について
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1029'
ht-degree: 62%

---

# ホスト

サイトと実稼動前の環境を整理し、[!DNL Adobe Target] での管理と環境別レポートを容易にします。

ホスト管理の主な目的は、非アクティブなコンテンツが誤って web サイトに表示されるのを確実に防ぐことです。ホスト管理では、レポートデータを[環境](/help/main/administrating-target/environments.md)ごとに分離することもできます。

ホストは、[!DNL Target] リクエストが行われる任意のドメインです。Web サイトでは、通常、[!DNL Target] リクエストを送信する URL の `location.hostname` プロパティです。

デフォルトでは、[!DNL Target] は、[!DNL Target] リクエストを行ったり [!DNL Target] レスポンスを受信できるホストを制限しません。新しいホストがリクエストを行うと、そのホストは自動的に機能します。このプロセスにより、不明なドメインや予期できないドメインでのテストも可能になります。 このデフォルトの動作を上書きする場合は、許可リストまたはブロックリストを設定して、[!DNL Target] で機能するホストを制限することができます。

ホストを管理するには、**[!UICONTROL Administration]**/**[!UICONTROL Hosts]** をクリックします。

![hosts_list image](assets/hosts_list.png)

## ホストの認識 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

ホストを認識し、[!UICONTROL Hosts] リストに追加するには、次の条件を満たす必要があります。

* 1 つ以上の [!DNL Target] リクエストがホストに存在する必要があります。
* ホスト上のページには、以下が含まれている必要があります。

   * 正しい mbox.js の参照
   * [!DNL Target] リクエストまたは自動生成されたグローバル [!DNL Target] リクエスト

* [!DNL Target] リクエストのあるページはブラウザーで表示する必要があります。

ページの表示後に、ホストが [!UICONTROL Hosts] リストに表示され、環境内でホストを管理したり、アクティビティとテストをプレビューしたり開始したりできます。

>[!NOTE]
>
>この説明は、個人で使用する開発サーバーも対象となります。

ホストが [!UICONTROL Host] リストに追加されたら、そのホストが認識されていることを確認します。

1. **[!UICONTROL Administration]**／**[!UICONTROL Hosts]**&#x200B;をクリックします。
1. ホストが一覧に表示されていない場合は、ブラウザーを更新します。

   デフォルトでは、新しく認識されたホストは [!UICONTROL Production] 環境に配置されます。 この [!UICONTROL Production] 環境は最も安全な環境です。なぜなら、これらのホストからは、非アクティブなアクティビティを表示できないからです。

1. （条件次第） **[!UICONTROL Move]** 動アイコン（![ 移動アイコン ](/help/main/administrating-target/assets/icon-move.png)）をクリックして、ホストを [!UICONTROL Development]、[!UICONTROL Staging]、またはその他の環境に移動します。

>[!NOTE]
>
>[!UICONTROL Production] 環境は、たとえ名前を変更したとしても、削除できません。 なぜなら、この環境で、最終のアクティブなキャンペーンとテストを扱うことを前提としているからです。このデフォルト環境では、非アクティブなキャンペーンの表示は許可されていません。

## ホストリストの並べ替えと検索 {#section_068B23C9D8224EB78BC3B7C8580251B0}

[!UICONTROL Hosts] リストを並べ替えるには、任意の列ヘッダー（[!UICONTROL Name]、[!UICONTROL Environment]、[!UICONTROL Last Requested]）をクリックして、昇順または降順で並べ替えます。

[!UICONTROL Hosts] リストを検索するには、検索語を [!UICONTROL Search Hosts] ボックスに入力します。

## [!DNL Target] リクエストを [!DNL Target] に送信できるホストを指定する許可リストの作成 {#allowlist}

[!DNL Target] リクエストを [!DNL Target] に送信できるホスト（ドメイン）を指定する許可リストを作成できます。この場合、許可リストにないホストがリクエストを生成すると、許可されていない旨を記した承認エラーレスポンスが送信されます。デフォルトでは、[!DNL Target] リクエストを含むホストは、[!UICONTROL Production] 環境の [!DNL Target] に登録され、アクティブで承認済みのすべてのアクティビティへのアクセス権を持ちます。 これが期待された手法でない場合は、代わりに許可リストを使用して、[!DNL Target] リクエストの生成と [!DNL Target] コンテンツの受け取りの資格がある特定のホストを記録できます。すべてのホストは、引き続き [!UICONTROL Hosts] リストに表示されます。また、環境では引き続きこれらのホストをグループ化したり、ホストごとに異なるレベル（ホストがアクティブまたは非アクティブなアクティビティを表示できるかどうかなど）を割り当てることができます。

許可リストを作成するには、次の手順を実行します。

1. [!UICONTROL Hosts] リストで、「**[!UICONTROL Authorize Hosts]**」をクリックします。
1. 「**[!UICONTROL Enable Authorized Hosts for content delivery]**」切替スイッチを有効にします。
1. 必要に応じて、**[!UICONTROL Host contains]** ボックスに目的のホストを追加します。

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. 必要に応じて、**[!UICONTROL Host does not contains]** ボックスに目的のホストを追加します。

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. **[!UICONTROL Save]** をクリックします。

許可されていないホストで [!DNL Target] リクエストが行われた場合、`/* no display - unauthorized mbox host */` というレスポンスが返されます。

>[!IMPORTANT]
>
>**セキュリティのベストプラクティス**:[!DNL Target] の ubox 機能を使用する場合、この許可リストは、[ リダイレクター ](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank} を使用した場合の移動先であるドメインのリストも制御します。 実装の一部として ubox を使用する場合は、リダイレクト先のドメインを必ず追加してください。許可リストが指定されない場合、[!DNL Adobe] は、リダイレクト URL を検証できず、悪意のあるリダイレクトの可能性から保護できません。
>
>許可リストは、環境よりも優先されます。許可リスト機能を使用する前に、すべてのホストをクリアしてください。すると、許可リストで許可されているホストのみがホストリストに表示されます。その後、ホストを必要な環境に移動できます。

場合によっては、他のサイトからのドメインが環境内に表示されることがあります。ドメインが at.js を呼び出すと、そのドメインがリストに表示されます。例えば、自分の web ページのいずれかが他のユーザーのサーバーにコピーされた場合は、そのサーバーのドメインが自分の環境に表示されます。スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることもあります。

`mboxHost` が API 呼び出しで渡される場合、渡される環境のコンバージョンが記録されます。環境が渡されない場合、この呼び出しでのホストは、デフォルトで [!UICONTROL Production] になります。

[!UICONTROL Host Does Not Contain] ールボックスに目的のホストを追加することで、[!DNL Target] にリクエストを送 [!DNL Target] できないホスト（ドメイン）を指定するブロックリストを作成することもできます。

>[!NOTE]
>
>[!UICONTROL Authorized Hosts] リストは、[!DNL Target] ホストとデフォルトのリダイレクトホストの両方に使用されます。 [!DNL Adobe Target] JavaScript SDK（at.js）の使用を許可されているすべての既存のドメイン、*および* ubox のデフォルトのリダイレクト URL で使用されるすべてのドメインを追加してください。今後、同様のドメインが新しく出てきた場合は、そのドメインを許可リストに追加してください。

## ホストの削除 {#section_F56355BA4BC54B078A1A8179BC954632}

不要になったホストは削除することができます。

1. [!UICONTROL Hosts] リストで、「**[!UICONTROL Delete]**」アイコンをクリックします。
1. 「**[!UICONTROL Delete]**」をクリックして削除を確認します。

>[!NOTE]
>
>削除されたホストで、[!DNL Target] リクエストを含むページが他のユーザーによって参照された場合、そのホストは再びリストに表示されます。

## ホストのトラブルシューティング {#concept_B3D7583FA4BB480382CC7453529FE1B7}

ホストにおいて問題が発生した場合は次のトラブルシューティングのヒントを試してください。

**ホストがアカウントのリストに表示されない。**

* ブラウザーで [!UICONTROL Hosts] ページを更新します。
* at.js の参照を含め、[!DNL Target] リクエストが正しいことを確認します。
* そのホストでいずれかの [!DNL Target] リクエストを参照します。ホスト上にあるどの [!DNL Target] リクエストも、これまでブラウザーでレンダリングされたことがなかった可能性があります。

**ランダムなドメインまたは不明なドメインが [!UICONTROL Host] リストに表示される。**

あるドメインから [!DNL Target] へのリクエストが行われると、そのドメインがリストに表示されます。場合によっては、スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることがあります。リストに表示されたドメインがチームで使用されていない場合は、「[!UICONTROL Delete]」をクリックして削除できます。

**[!DNL Target] リクエストで「/&#42; no display - unauthorized mbox host &#42;/」が返される。**

許可されていないホストで [!DNL Target] リクエストが行われた場合、「/&#42; no display - unauthorized mbox host &#42;/」というレスポンスが返されます。
