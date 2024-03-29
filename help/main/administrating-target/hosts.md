---
keywords: ホスト;ホスト;ホストグループ;トラブルシューティング;ベストプラクティス;ubox;リダイレクト;リダイレクト;ホワイトリスト;許可リスト;ブラックリスト;ブロックリスト
description: Adobe Target での管理と環境別レポートを容易に行えるように web サイトと実稼動前の環境を整理する方法について説明します。
title: ホストおよびその使用方法について
feature: Administration & Configuration
role: Admin
exl-id: 31c661c0-686d-440e-ad58-864fb853b1c4
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '1088'
ht-degree: 95%

---

# ホスト

サイトと実稼動前の環境を整理し、[!DNL Adobe Target] での管理と環境別レポートを容易にします。

ホスト管理の主な目的は、非アクティブなコンテンツが誤って web サイトに表示されるのを確実に防ぐことです。ホスト管理では、レポートデータを[環境](/help/main/administrating-target/environments.md)ごとに分離することもできます。

ホストは、[!DNL Target] リクエストが行われる任意のドメインです。Web サイトでは、通常、[!DNL Target] リクエストを送信する URL の `location.hostname` プロパティです。

デフォルトでは、[!DNL Target] は、[!DNL Target] リクエストを行ったり [!DNL Target] レスポンスを受信できるホストを制限しません。新しいホストがリクエストを行うと、そのホストは自動的に機能します。また、このプロセスにより、不明なドメインや予期できないドメインでのテストも可能になります。 このデフォルトの動作を上書きする場合は、許可リストまたはブロックリストを設定して、[!DNL Target] で機能するホストを制限することができます。

ホストを管理するには、**[!UICONTROL 管理]**／**[!UICONTROL ホスト]**&#x200B;をクリックします。

![hosts_list 画像](assets/hosts_list.png)

## ホストの認識 {#concept_0D4B43E23AA9408F8B28A57ED754BF65}

ホストを認識し、[!UICONTROL ホスト]リストに含めるには、次の条件を満たす必要があります。

* 1 つ以上の [!DNL Target] リクエストがホストに存在する必要があります。
* ホスト上のページには、以下のものが含まれている必要があります。

   * 正しい mbox.js の参照
   * [!DNL Target] リクエストまたは自動生成されたグローバル [!DNL Target] リクエスト

* [!DNL Target] リクエストのあるページはブラウザーで表示する必要があります。

ページの表示後に、ホストが[!UICONTROL ホスト]リストに表示され、環境内でホストを管理したり、アクティビティとテストをプレビューしたり開始したりできます。

>[!NOTE]
>
>この説明は、個人で使用する開発サーバーも対象となります。

ホストが[!UICONTROL ホスト]リストに追加された後、確実にホストが認識されるようにします。

1. **[!UICONTROL 管理]**／**[!UICONTROL ホスト]**&#x200B;をクリックします。
1. ホストが一覧に表示されていない場合は、ブラウザーを更新します。

   デフォルトでは、新しく認識されたホストは[!UICONTROL 実稼動]環境に配置されます。この[!UICONTROL 実稼動]環境は最も安全な環境です。なぜなら、実稼動環境に属するホストからは、非アクティブなアクティビティを表示できないからです。

1. （条件次第）**[!UICONTROL 移動]**&#x200B;アイコン（![移動アイコン](/help/main/administrating-target/assets/icon-move.png)）をクリックして、ホストを[!UICONTROL 開発]環境、[!UICONTROL ステージング]環境、または他の環境に移動します。

>[!NOTE]
>
>[!UICONTROL 実稼動]環境は、たとえ名前を変更したとしても、削除できません。なぜなら、この環境で、最終のアクティブなキャンペーンとテストを扱うことを前提としているからです。このデフォルト環境では、非アクティブなキャンペーンの表示は許可されていません。

## ホストリストの並べ替えと検索 {#section_068B23C9D8224EB78BC3B7C8580251B0}

[!UICONTROL ホスト]リストを並べ替えるには、任意の列ヘッダー（[!UICONTROL 名前]、[!UICONTROL 環境]、[!UICONTROL 最終リクエスト]）をクリックして、昇順または降順で並べ替えます。

[!UICONTROL ホスト]リストを検索するには、「[!UICONTROL ホストを検索]」ボックスに検索語を入力します。

## [!DNL Target] リクエストを [!DNL Target] に送信できるホストを指定する許可リストの作成 {#allowlist}

[!DNL Target] リクエストを [!DNL Target] に送信できるホスト（ドメイン）を指定する許可リストを作成できます。この場合、許可リストにないホストがリクエストを生成すると、許可されていない旨を記した承認エラーレスポンスが送信されます。デフォルトでは、[!DNL Target] リクエストを含むホストは、[!UICONTROL 実稼動]環境の [!DNL Target] に登録され、アクティブで承認済みのすべてのキャンペーンへのアクセス権を持ちます。これが期待された手法でない場合は、代わりに許可リストを使用して、[!DNL Target] リクエストの生成と [!DNL Target] コンテンツの受け取りの資格がある特定のホストを記録できます。すべてのホストは、[!UICONTROL ホスト]リストに引き続き表示されます。また、環境では引き続きこれらのホストをグループ化したり、ホストごとに異なるレベル（ホストがアクティブまたは非アクティブなアクティビティを表示できるかどうかなど）を割り当てることができます。

許可リストを作成するには、次の手順を実行します。

1. [!UICONTROL ホスト]リストから、「**[!UICONTROL ホストを認証]**」をクリックします。
1. 「**[!UICONTROL コンテンツ配信用に認証済みホストを有効にする]**」を有効に切り替えます。
1. 必要に応じて、「**[!UICONTROL ホストに含む]**」ボックスに目的のホストを追加します。

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. 必要に応じて、「**[!UICONTROL ホストに含めない]**」ボックスに目的のホストを追加します。

   複数のホストを追加することもできます。この場合、1 行に 1 つずつ表示されます。

1. 「**[!UICONTROL 保存]**」をクリックします。

許可されていないホストで [!DNL Target] リクエストが行われた場合、`/* no display - unauthorized mbox host */` というレスポンスが返されます。

>[!IMPORTANT]
>
>**セキュリティのベストプラクティス**：[!DNL Target] の ubox 機能を使用すると、[リダイレクター](https://experienceleague.adobe.com/docs/target-dev/developer/implement-email/working-with-redirectors.html){target=_blank}を使用した場合の移動先であるドメインのリストも、この許可リストで管理できます。実装の一部として ubox を使用する場合は、リダイレクト先のドメインを必ず追加してください。許可リストが指定されない場合、[!DNL Adobe] は、リダイレクト URL を検証できず、悪意のあるリダイレクトの可能性から保護できません。
>
>許可リストは、環境よりも優先されます。許可リスト機能を使用する前に、すべてのホストをクリアしてください。すると、許可リストで許可されているホストのみがホストリストに表示されます。その後、ホストを必要な環境に移動できます。

場合によっては、他のサイトからのドメインが環境内に表示されることがあります。ドメインが at.js を呼び出すと、そのドメインがリストに表示されます。例えば、自分の web ページのいずれかが他のユーザーのサーバーにコピーされた場合は、そのサーバーのドメインが自分の環境に表示されます。スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることもあります。

`mboxHost` が API 呼び出しで渡される場合、渡される環境のコンバージョンが記録されます。環境が渡されない場合、この呼び出しでのホストは、デフォルトの「[!UICONTROL Production]」になります。

目的のホストを「[!UICONTROL ホストに含めない]」ボックスに追加して、[!DNL Target] リクエストを [!DNL Target] に送信できないホスト（ドメイン）を指定するブロックリストを作成することもできます。

>[!NOTE]
>
>[!UICONTROL 認証済みホスト]リストは、[!DNL Target] ホストとデフォルトのリダイレクトホストの両方に使用されます。[!DNL Adobe Target] JavaScript SDK（at.js）の使用を許可されているすべての既存のドメイン、*および* ubox のデフォルトのリダイレクト URL で使用されるすべてのドメインを追加してください。今後、同様のドメインが新しく出てきた場合は、そのドメインを許可リストに追加してください。

## ホストの削除 {#section_F56355BA4BC54B078A1A8179BC954632}

不要になったホストは削除することができます。

1. [!UICONTROL ホスト]リストで、「**[!UICONTROL 削除]**」アイコンをクリックします。
1. 「**[!UICONTROL 削除]**」をクリックして削除を確定します。

>[!NOTE]
>
>削除されたホストで、[!DNL Target] リクエストを含むページが他のユーザーによって参照された場合、そのホストは再びリストに表示されます。

## ホストのトラブルシューティング {#concept_B3D7583FA4BB480382CC7453529FE1B7}

ホストにおいて問題が発生した場合は次のトラブルシューティングのヒントを試してください。

**ホストがアカウントのリストに表示されない。**

* ブラウザーで[!UICONTROL ホスト]ページを再読み込みします。
* at.js の参照を含め、[!DNL Target] リクエストが正しいことを確認します。
* そのホストでいずれかの [!DNL Target] リクエストを参照します。ホスト上にあるどの [!DNL Target] リクエストも、これまでブラウザーでレンダリングされたことがなかった可能性があります。

**ランダムなドメインまたは不明なドメインが[!UICONTROL ホスト]リストに表示される。**

あるドメインから [!DNL Target] へのリクエストが行われると、そのドメインがリストに表示されます。場合によっては、スパイダーエンジン、言語翻訳サイトまたはローカルディスクドライブからのドメインが表示されることがあります。表示されるドメインがチームで使用していないドメインである場合は、「[!UICONTROL 削除]」をクリックして、そのドメインを削除します。

**マイ [!DNL Target] リクエストが返す/&#42; 表示なし — 許可されていない mbox ホスト &#42;/.**

次の場合、 [!DNL Target] リクエストが権限のないホストでおこなわれ、リクエストへの応答は/になります。&#42; 表示なし — 許可されていない mbox ホスト &#42;/.
