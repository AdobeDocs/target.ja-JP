---
keywords: 実装;mbox.js 非 JavaScript;リダイレクター;クリックあたりのコスト;クリックあたりの売上高
description: Adobeで mbox を使用する方法と同様に、電子メール実装でリダイレクターを使用する方法について説明します。 [!DNL Target] アクティビティ。
title: リダイレクターの使用方法
feature: Implement Email
role: Developer
exl-id: 1e7b99e4-857b-4d0f-afbd-2c5ce6bf0557
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 68%

---

# リダイレクターの使用

リダイレクターは、テストで mbox を使用する場合と同様に使用します。

リダイレクターは、リダイレクター mbox（リダイレクター）をアカウントにロードする特殊なリダイレクターの URL を使用して作成されます。このリダイレクターは、テストで mbox を使用する場合と同様に使用します。リダイレクターの URL を広告ネットワークに広告の表示先リンクとして送信します。

リダイレクターの使用目的は次のとおりです。

* ディスプレイ広告からサイトへのクリックの追跡
* 複数の広告ネットワーク上のディスプレイ広告に対するクリックを追跡するための、一元管理された単一のレポートの作成
* ディスプレイ広告の表示先の変更

   例えば、同じバナーはホームページ、カテゴリページおよび製品紹介ページにランディングします。

* 最もコンバージョン率の高いランディングページの発見

適切な設定の判断方法については、[JavaScript ベース以外の実装](https://developer.adobe.com/target/implement/email/).

## リダイレクターの作成 {#redirector}

リダイレクターを使用するには、まずリダイレクターを作成する必要があります。

1. 広告の様々な表示先（デフォルトの表示先を含む）を決定します。
1. リダイレクターの URL を作成します。

   ```
   https://<your_testandtarget_clientcode>.tt.omtrdc.net/​m2/yourclientcode/ubox
   /​page?mbox=redirectorlink_456
   &mboxDefault=http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm
   ```

   * `yourclientcode` はお客様のクライアントコードです。クライアントコードはすべて小文字で、特殊文字は含まれません。

      クライアントコードは [!UICONTROL 管理/実装] ページ [!DNL Target] インターフェイス。

   * `redirectorlink_456` は、キャンペーンおよびテストで使用するためにアカウントで表示するリダイレクター mbox の名前です。

      リダイレクターの機能は他の mbox とは異なりますが、他の mbox と同様にアカウントで表示されます。アカウント内の標準タイプの mbox と区別しやすいようなリダイレクターの名前を指定してください。mbox の名前には、&#39;redirectorlink&#39; を先頭に付けることをお勧めします。

   * `http%3A%2F%2Fwww%2Eyourcompany%2Ecom%2Fusualdestination%2Ehtm` はデフォルトの宛先です。

      URL エンコードをおこない、絶対参照にする必要があります。以下を使用して、 [HTMLURL エンコーディングのリファレンス](https://www.w3schools.com/tags/ref_urlencode.asp) を使用して、URL を簡単にエンコードできます。

      >[!IMPORTANT]
      >
      >リダイレクターを使用すると、オープンリダイレクトの脆弱性のリスクにさらされる可能性があることに注意してください。 サードパーティによるリダイレクターリンクの不正使用を防ぐため、「認証済みホスト」を使用してデフォルトのリダイレクト URL ドメインをす許可リストることをお勧めします。 Target は、ホストを使用して、リダイレクトを許可するドメインを許可リストに登録します。詳しくは、[ホスト&#x200B;*の](/help/main/administrating-target/hosts.md#allowlist)Target に mbox 呼び出しを送信する権限のあるホストを指定する許可リストの作成*&#x200B;を参照してください。

1. リダイレクターを検証します。
   1. *セキュリティのベストプラクティス*:上記のように、リダイレクターで使用するドメインが許可リストに加えるされていることを確認します。 許可リストに加えるされていないドメインを使用する場合、Adobeは、悪意のあるアクターがリダイレクターを使用して悪意のあるドメインにリダイレクトするのを防ぐために、そのドメインへの呼び出しをブロックします。
   1. リダイレクターの URL をブラウザーに挿入して表示を更新します。
   1. アカウントにログインし、mbox のリストを更新して、新しいリダイレクターが mbox として表示されることを確認します。
1. 1 つの広告に対してさまざまな表示先をテストする場合、各バージョンごとに[リダイレクトオファー](/help/main/c-experiences/c-visual-experience-composer/redirect-offer.md#task_9578678D42784F5EB9638F8AC8C911FA)を作成します。
1. キャンペーンを作成します。

   詳しくは、 [JavaScript ベース以外の実装](https://developer.adobe.com/target/implement/email/){target=_blank} を参照してください。
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

## リダイレクターを使用してクリックあたりのコストとクリックあたりの売上高を渡す {#concept_3078EF48E9C44B34992D62AAB9628853}

リダイレクターを使用してクリックあたりのコストとクリックあたりの売上高を渡す方法について説明します。

### クリックあたりのコストを渡す {#section_DEB889470F7D4360B5CEA85FD05DEDFA}

リダイレクターを使用して、クリックあたりのコストを引き渡すことができます。

>[!NOTE]
>
>ベストプラクティスは、 **訪問あたりのスコア** エンゲージメント指標。

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
>ベストプラクティスは、 **訪問あたりのスコア** エンゲージメント指標。

`&mboxPageValue=value` を URL に追加します。

例：クリックあたり 10 セントの売上高の場合

```
https://<​your_clientcode>​​​​.tt​​.omtrdc​.net/​​m2/​yourclientcode/​ubox/​​​page?mbox=redirectorlink_456
&mboxPageValue=0.1​&mbox​Default=​​http%3A%2F%2Fwww%2E​yourcompany%2Ecom​%2Fusualdestination%2Ehtm
```
