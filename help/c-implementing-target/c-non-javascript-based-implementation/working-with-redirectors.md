---
keywords: Implementation;mbox.js non javascript;redirector;costs per click;revenue per click
description: リダイレクターは、テストで mbox を使用する場合と同様に使用します。
title: リダイレクターの使用
feature: null
subtopic: Getting Started
topic: Standard
uuid: 79d7caf6-5693-4bb3-9131-8d1ae420fa5e
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '659'
ht-degree: 69%

---


# リダイレクターの使用{#work-with-redirectors}

リダイレクターは、テストで mbox を使用する場合と同様に使用します。

リダイレクターは、リダイレクター mbox（リダイレクター）をアカウントにロードする特殊なリダイレクターの URL を使用して作成されます。このリダイレクターは、テストで mbox を使用する場合と同様に使用します。リダイレクターの URL を広告ネットワークに広告の表示先リンクとして送信します。

リダイレクターの使用目的は次のとおりです。

* ディスプレイ広告からサイトへのクリックの追跡
* 複数の広告ネットワーク上のディスプレイ広告に対するクリックを追跡するための、一元管理された単一のレポートの作成
* ディスプレイ広告の表示先の変更

   例えば、同じバナーはホームページ、カテゴリページおよび製品紹介ページにランディングします。

* 最もコンバージョン率の高いランディングページの発見

適切な設定の判断方法については、[JavaScript ベース以外の実装](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4).

## Create a redirector {#redirector}

リダイレクターを使用するには、まずリダイレクターを作成する必要があります。

1. 広告の様々な表示先（デフォルトの表示先を含む）を決定します。
1. リダイレクターの URL を作成します。

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * `yourclientcode` はお客様のクライアントコードです。クライアントコードはすべて小文字で、特殊文字は含まれません。

      Your client code is available at the top of the [!UICONTROL Administration > Implementation] page of the [!DNL Target] interface.

   * `redirectorlink_456` は、キャンペーンおよびテストで使用するためにアカウントで表示するリダイレクター mbox の名前です。

      リダイレクターの機能は他の mbox とは異なりますが、他の mbox と同様にアカウントで表示されます。アカウント内の標準タイプの mbox と区別しやすいようなリダイレクターの名前を指定してください。mbox の名前には、&#39;redirectorlink&#39; を先頭に付けることをお勧めします。

   * `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` はデフォルトの宛先です。

      URL エンコードをおこない、絶対参照にする必要があります。You can use the [HTML URL Encoding Reference](https://www.w3schools.com/tags/ref_urlencode.asp) to quickly encodes your URLs.

      >[!IMPORTANT]
      >
      >リダイレクターを使用すると、オープンリダイレクトの脆弱性が発生するリスクがあることに注意してください。 サードパーティによるリダイレクターリンクの不正使用を防ぐために、デフォルトのリダイレクトURLドメインを許可リストする際に、「認証済みホスト」を使用することをお勧めします。 ターゲットは、リダイレクトを許可する許可リストドメインに対してホストを使用します。 詳しくは、「 [Hosts](/help/administrating-target/hosts.md#allowlist) 」のターゲットにmbox呼び出しを送信する権限のあるホストを指定する許可リストの *作成を参照してください*。

1. リダイレクターを検証します。
   1. *セキュリティのベストプラクティス*:上記のように、リダイレクターで使用するドメインが許可されていることを確認します。 許可されていないドメインを使用すると、Adobeは、悪意のあるアクターがリダイレクターを使用して悪質なドメインにリダイレクトするのを防ぐために、そのドメインへの呼び出しをブロックします。
   1. リダイレクターの URL をブラウザーに挿入して表示を更新します。
   1. アカウントにログインし、mbox のリストを更新して、新しいリダイレクターが mbox として表示されることを確認します。
1. 1 つの広告に対してさまざまな表示先をテストする場合、各バージョンごとに[リダイレクトオファー](../../c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を作成します。
1. キャンペーンを作成します。

   目的に合わせた適切な設定については、「[JavaScript ベース以外の実装](../../c-implementing-target/c-non-javascript-based-implementation/non-javascript-based-implementation.md#concept_4799C58B081A43F6B3B8CC25A8D5D7C4)」を参照してください。
1. キャンペーンで QA を完了します。

   リダイレクターの URL を含む `<a href>` を使用してダミーページを作成します。例：

   ```
   <a href=https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=
   
   redirectorlink_456&mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2F​usualdestination%2Ehtm>
   ```

1. あらゆる環境のすべてのタイプのブラウザーで、エクスペリエンス、デフォルトコンテンツおよびレポートがすべて期待どおりに機能することを確認します。

   >[!NOTE]
   >
   >* リダイレクターは、オファープレビューまたは mbox の閲覧ではサポートされていません。ブラウザーで直接エクスペリエンスのプレビューを確認してください。
   >* `mboxDebug` はリダイレクターでは機能しません。


1. リダイレクターの完全な URL をディスプレイ広告ネットワークに広告の表示先として送信します。

## Use a redirector to pass Costs per Click and Revenue Per Click {#concept_3078EF48E9C44B34992D62AAB9628853}

リダイレクターを使用してクリックあたりのコストとクリックあたりの売上高を渡す方法について説明します。

### クリックあたりのコストを渡す {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

リダイレクターを使用して、クリックあたりのコストを引き渡すことができます。

>[!NOTE]
>
>Best practice is to determine the cost value using the **Score per visit** engagement metric.

`&mboxPageValue=-value` を URL に追加します。負の値であることに注意してください。

例：クリックあたり 10 セントのコストの場合

```
https://<your_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox/​page?mbox=redirectorlink_456
&mboxPageValue=-0.1&mboxDefault=​https://www.yourcompany.com/usualdestination.htm
```

### クリックあたりの売上高を渡す {#section_3E48AC465E7D42DAAC51B4BFF83F64B1}

リダイレクターを使用して、クリックあたりの売上高を引き渡すことができます。

>[!NOTE]
>
>Best practice is to determine the revenue value using the **Score per visit** engagement metric.

`&mboxPageValue=value` を URL に追加します。

例：クリックあたり 10 セントの売上高の場合

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
